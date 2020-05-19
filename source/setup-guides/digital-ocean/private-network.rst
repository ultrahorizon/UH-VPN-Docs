Digital Ocean Private Networks
==============================

Digital Ocean has the ability to allow Droplets to communicate over a private network. Digital Ocean
does this over a separate interface ``eth1``. In order to use this interface and allow UH VPN
clients to reach Droplets over the private network, some ``iptables`` rules need to be added.

Step 1: Determine the private subnet
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

First login to the `Digital Ocean`_ control panel navigate to a Droplet using private networking,
click on the "Networking" tab and scroll down to the "Private Networking" section:

.. image:: /_static/setup-guides/private-network.png
  :width: 600
  :alt: Private network

In the image above the private network is ``10.106.0.0/20``. Note yours down as it'll be used later.

Step 2: Add iptables rules
~~~~~~~~~~~~~~~~~~~~~~~~~~

Digital Ocean uses a separate interface for private networking and so the default NAT rule inserted
by the UH VPN server does not cater for the private subnet. To rectify this one must first SSH into
the Droplet and determine the interface used for the private network by executing the command:

.. code-block:: bash

    route

.. image:: /_static/setup-guides/route.png
  :width: 600
  :alt: Private network

In the above example, it is possible to see that the ``eth1`` interface is used by Digital Ocean
for the network ``10.106.0.0/20``.

Next it's time to add the appropriate iptable rule. In order to do this one must first know the
tunnel network used on the UH VPN Server. To obtain this head over to the UH VPN `website`_ and
within the relevant group click the |edit_icon| next to the server in question. Then note down
the tunnel network.

.. image:: /_static/setup-guides/tunnel-network.png
  :width: 600
  :alt: Private network

In the above example, the tunnel network is: ``172.31.255.0/24``

Finally, to enable connectivity from UH VPN clients to the Digital Ocean private network execute
the following command:

.. code-block:: bash

    iptables --table nat --append POSTROUTING -s 172.31.255.0/24 --out-interface eth1 -j MASQUERADE

where ``172.31.255.0/24`` and ``eth1`` are replaced with your own tunnel network and interface
respectively.

At this point one should attempt to connect to the UH VPN Server and check to ensure that
connecting clients are able to reach other Droplets within the private network.

Step 3: Ensure persistent reboots
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

iptables commands are not persistent across reboots. This means that every time a server is rebooted,
the rule providing connectivity to the private network is removed. To avoid this problem, it is necessary
to insert the iptables command used above into ``/etc/rc.local`` so that it is executed on boot.

To do this first edit the file ``/etc/rc.local``:

.. code-block:: bash

    nano /etc/rc.local

Then add the command you used above into the file:

.. image:: /_static/setup-guides/rc-local.png
  :width: 600
  :alt: rc.local

Then save the file (Ctrl-X) in nano. This will ensure that the rule is inserted every time the
server is booted.

.. note::
    It is imperative that you update this rule if you change the tunnel network in the UH VPN
    Server settings.

Premium Enhancements
~~~~~~~~~~~~~~~~~~~~

It is quite common for cloud users to only want traffic destined for the Digital Ocean private
network to be routed over the VPN instead of their entire Internet connection. This is to avoid
extra charges from Digital Ocean if bandwidth/data exceeds the monthly allowance.

This can be easily accomplished via UH VPN's custom IP routing (a premium plan feature). To enable this
functionality head over to the `website`_ and within the relevant group click the |edit_icon|
next to the server in question.

Ensure that both buttons, "Redirect all IPv4 Traffic" and "Redirect all IPv6 Traffic" are switched off,
then proceed to add your Digital Ocean private network into IPv4 selection box and leave the IPv6
selection box blank:

.. image:: /_static/setup-guides/custom-routing.png
  :width: 600
  :alt: Custom Routing

Then save the server. Once this is done, connecting clients will only be pushed the routes for the Digital

.. _Digital Ocean: https://www.digitalocean.com/
.. _website: https://uh-vpn.com
.. |edit_icon| image:: /_static/icons/pencil.svg
  :alt: Edit Icon