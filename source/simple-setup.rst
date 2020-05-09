Simple Setup Guide
==================

This guide is a walkthrough tutorial on setting up UH VPN. It contains step by step instructions
on how to provision a private cloud server along with all the necessary steps on setting up UH VPN
client applications.

The guide uses the cloud provider `Digital Ocean`_ to create servers for UH VPN as it's simple and
ideal for beginners, but this can be substituted for any other cloud provider (AWS, Azure etc...)
or an on-premise server if you have one.

If you wish to explore UH VPN advanced options or modify the sample deployments consult the extensive
documentation on this site.

- `Step 1: Create a Digital Ocean Server`_
- `Step 2: Create a Server on the UH VPN Website`_
- `Step 3: Setting up the Droplet with UH VPN`_
- `Step 4: Installing Client Apps`_


Step 1: Create a Digital Ocean Server
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

First create an account or login at: `Digital Ocean`_. Then click the "Create Droplets" button as shown in
the screenshot below:

.. image:: /_static/simple-setup/do-landing.png
  :width: 600
  :alt: DO Landing Page

One is then presented with a droplet creation page as follows:

.. image:: /_static/simple-setup/droplet-creation.png
  :width: 600
  :alt: Droplet Creation Page

Ensure the settings are selected as shown below:

- **Distribution** : Ubuntu 18.04
- **Plan** : Standard
- **Price** : $5 per month
- **Region** : Choose location closest to you unless you have a specific requirement
- **VPC** : No VPC
- **Additional Options** : None
- **SSH Key** : Select one-time password unless you're familiar with SSH (if so upload your public key).
- **Number of Droplets** : 1
- **Hostname** : Any friendly name you'd like to give to your server. E.g. "UH-VPN".
- **Tags** : None
- **Backups** : None

Then press create! The droplet will then begin provisioning and a page similar to the one shown below will
appear:

.. image:: /_static/simple-setup/droplet-provision.png
  :width: 600
  :alt: Droplet Provisioning Page

Once the provisioning stage has completed, click on the droplet and one will be presented with a page detailing
all aspects of the droplet:

.. image:: /_static/simple-setup/droplet-overview.png
  :width: 600
  :alt: Droplet Overview Page

Note down the IPv4 address of the droplet as we'll use this later on the UH VPN website. Then click the networking
tab in the droplet overview page. Scroll to the bottom and under the firewalls section press the "Edit" button.

.. image:: /_static/simple-setup/create-firewall.png
  :width: 600
  :alt: Firewall Creation Page

Press the create button, choose a name for the firewall E.g. UH-VPN-Firewall, then ensure the rules
are defined to match the specification below:

.. image:: /_static/simple-setup/inbound-rules.png
  :width: 600
  :alt: Inbound Rules

.. image:: /_static/simple-setup/outbound-rules.png
  :width: 600
  :alt: Outbound Rules

.. note::
    If you are connecting to your instance via SSH, then also add rules to allow SSH connections to the
    Droplet.

Finally, ensure the firewall is associated to the droplet you created earlier. E.g. UH-VPN. Then
press "Create Firewall". The Droplet is now firewalled against adversaries and ready for UH VPN.

Step 2: Create a Server on the UH VPN Website
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The UH VPN `website`_ is the command and control centre for the VPN deployment. All VPN settings
are managed through this interface. The first step (if you haven't done so already) is to
`create an account`_. Then once logged in, click the management tab and then press the
"Create New Group" button. One is then presented with the following page:

.. image:: /_static/simple-setup/create-group.png
  :width: 600
  :alt: Create Group Page

If you're just using UH VPN for personal use, go ahead and click the "Free Plan" button. However,
if you'd like access to advanced features such as custom app branding, unlimited devices and more,
then choose the premium plan. A breakdown of the options can be seen on the `Creating Groups`_ docs page.

Choose an appropriate name for the group E.g. Personal and then leave the timeout set at 86400.
Then press the "Submit" button and the group will be created.

Click on the group name that has just been created and the following page will be presented:

.. image:: /_static/simple-setup/group-page.png
  :width: 600
  :alt: Group Page

The first step is to create a UH VPN server, click the "Create New Server" button and the following
page will be presented:

.. image:: /_static/simple-setup/create-server.png
  :width: 600
  :alt: Create New Server

Enter the following parameters:

* **Name** : UDP
* **Appearance Order** : 0
* **Domain/IP Address** : IPv4 Address noted from the Digital Ocean droplet earlier
* **Port** : 443
* **UDP** : Enabled
* **IPv4 Tunnel Network** : 172.31.255.0/24
* **IPv6 Tunnel Network** : fe80::/64
* **DNS Servers** : 1.1.1.1, 1.0.0.1
* **Add Forwarding Rule** : Enabled
* **Add NAT Rule** : Enabled

Press submit and the server will then be created.

.. note::
    A full description of all parameters can be found on the `server creation docs page`_.

Once created, press the |key_icon| icon to obtain a UH VPN API token for the server. Copy
and paste this to somewhere safe as it'll be used later.

Step 3: Setting up the Droplet with UH VPN
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If you configured the droplet earlier using SSH keys then SSH into your droplet now, otherwise
head over to `Digital Ocean`_. Then click on the droplet you created earlier, click the "Access" Tab
and press the "Launch Console" button. A popup will display:

.. image:: /_static/simple-setup/console-popup.png
  :width: 300
  :alt: Console Popup

Login to the droplet using the username "root" and the password emailed to you by Digital Ocean.
If you didn't set up the droplet with SSH, you'll be asked to set a password when first logging
in.

The first step is to add Ultra Horizon's package archive to the system sources.

.. code-block:: bash

    $> sudo add-apt-repository ppa:ultrahorizon/ppa

.. image:: /_static/simple-setup/ppa-confirm.png
  :width: 500
  :alt: PPA Confirm

A prompt will then display information about the repository, accept this, then download the package information
from this newly added archive:

.. code-block:: bash

    $> sudo apt-get update

Once this is done, UH VPN Server software can now be downloaded through the apt package manager.

.. code-block:: bash

    $> sudo apt-get install uh-vpn-server

Once installed check that the UH VPN Service is running:

.. code-block:: bash

    $> sudo service uh-vpn-server status

The output should say **active (running)** as depicted below:

.. image:: /_static/servers/service_status.png
  :width: 600
  :alt: Expected status

Then to ensure UH VPN Server starts at boot, issue the following command:

.. code-block:: bash

    $> sudo systemctl enable uh-vpn-server

Next it's time to add the UH VPN Server API token we obtained earlier. This will
enable the UH VPN Server software to set up the VPN server on our Droplet.

.. code-block:: bash

    $> sudo nano /etc/uh-vpn-server/tokens

This will bring up an editor prompt like so:

.. image:: /_static/servers/token_store.png
  :width: 600
  :alt: Token store

In this example, the token (``0123456...``) has been appended to the file. Once this is done,
save the file and exit the editor (Ctrl-X in nano).

The server is now configured and it's safe to logout of the Droplet.

.. note::
    For advanced configurations of the server software follow the `server documentation`_.

Step 4: Installing Client Apps
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This is the final step in the set up process. First login to the UH VPN `website`_ and navigate
to the group you created earlier. Now it's time to make a new person who's authorised to access
the VPN server you just created. Click the "Create New Person" button and the following
page will be presented:

.. image:: /_static/simple-setup/create-person.png
  :width: 600
  :alt: Create New Person

Enter your name and email address, then press submit and the person will then be created.

Next it's time to associate a device to the person that's just been created. To do so, click the
name of the person and then press the "Add new device" button and the following page
will be presented:

.. image:: /_static/simple-setup/create-device.png
  :width: 600
  :alt: Create New Device

Enter the following parameters:

* **Name** : A name for the device. E.g. Android
* **Expiry Date** : Leave unfilled unless you wish to specify a date for device revocation
* **Expiry Time** : Leave unfilled unless you wish to specify a time for device revocation

.. note::
    A full description of all parameters can be found on the `device creation docs page`_.

Press submit and the device will then be created. You will then receive an email with a one-time
passcode (OTP). Download the UH VPN app for your platform and enter the OTP code to download
the profile. Then you can **connect and enjoy a fast, secure and private VPN connection!**

.. tip::
    Instructions for client apps can be found on the `clients docs page`_.


.. _Digital Ocean: https://www.digitalocean.com/
.. _installation instructions: servers/installation.html
.. _website: https://uh-vpn.com
.. _create an account: https://uh-vpn.com/auth/signup
.. _Creating Groups: website/groups/creating.html
.. _server creation docs page: website/servers/creating.html
.. |key_icon| image:: /_static/icons/key.svg
  :alt: Key Icon
.. _server documentation: servers/index.html
.. _device creation docs page: website/devices/creating.html
.. _clients docs page: clients/index.html