Reject inter-client communication
=================================

In certain scenarios, it may be desirable to prevent VPN clients communicating with one another. For example,
when running a public VPN service through UH VPN.

This can be achieved by disabling the "Add Forwarding Rules" button on the UH VPN server settings page and instead
inserting your own rules into ``iptables`` on your server as follows:

.. code-block::

    iptables --append FORWARD -s 172.31.255.0/24 -d 172.31.255.0/24 -j DROP
    iptables --append FORWARD -s 172.31.255.0/24 -j ACCEPT


Modify the above example to suit your tunnel network (replace ``172.31.255.0/24`` as appropriate).
These rules will drop inter-client communication, but allow all other communication.

.. tip:: Use the ``iptables-save`` package to persist ``iptables`` rules between reboots.