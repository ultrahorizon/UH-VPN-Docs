AWS Simple Setup Guide
======================

This guide is a walkthrough tutorial on setting up UH VPN on `AWS`_. It contains step by step
instructions on how to provision a private cloud server along with all the necessary steps on setting
up UH VPN client applications.

The guide makes use of the publicly available AMI on the AWS marketplace to create servers for UH VPN
as this provisioning technique allows an entire UH VPN deployment to be set up in less than 5 minutes!

- `Step 1: Create an AWS Instance`_
- `Step 2: Create a Server on the UH VPN Website`_
- `Step 3: Configuring the Instance`_
- `Step 4: Installing Client Apps`_


Step 1: Create an AWS Instance
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

First create an account or login at: `AWS`_. Then head over to the EC2 page and create a new instance
from the UH VPN AMI. Use an instance size appropriate for your needs and ensure that a security group
is configured allowing traffic:

- UDP 443 from Anywhere
- TCP 22 from Anywhere

Once launched, note down the public IPv4 address of the instance as this will be used later.

Step 2: Create a Server on the UH VPN Website
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The UH VPN `website`_ is the command and control centre for the VPN deployment. All VPN settings
are managed through this interface. The first step (if you haven't done so already) is to
`create an account`_. Then once logged in, click the management tab and then press the
"Create New Group" button. One is then presented with the following page:

.. image:: /_static/setup-guides/create-group.png
  :width: 600
  :alt: Create Group Page

If you're just using UH VPN for personal use, go ahead and click the "Free Plan" button. However,
if you'd like access to advanced features such as custom app branding, unlimited devices and advanced
VPN options, then choose the premium plan. A breakdown of the options can be seen on the
`Creating Groups`_ docs page.

Choose an appropriate name for the group E.g. Personal and then leave the timeout set at 86400.
Then press the "Submit" button and the group will be created.

Click on the group name that has just been created and the following page will be presented:

.. image:: /_static/setup-guides/group-page.png
  :width: 600
  :alt: Group Page

The first step is to create a UH VPN server, click the "Create New Server" button and the following
page will be presented:

.. image:: /_static/setup-guides/create-server.png
  :width: 600
  :alt: Create New Server

Enter the following parameters:

* **Name** : UDP
* **Appearance Order** : 0
* **Domain/IP Address** : IPv4 Address noted from the AWS instance earlier
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

Step 3: Configuring the Instance
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Login to the newly created instance via SSH using the username "ubuntu". Once logged in, a UH VPN
setup script will appear:

.. image:: /_static/setup-guides/setup-wizard.png
  :width: 400
  :alt: Setup Wizard

Simply paste the UH VPN API token obtained in step 2 into the prompt and press Enter:

.. image:: /_static/setup-guides/prompt.png
  :width: 450
  :alt: Prompt

Only one token is going to be added as we only wish to associate one server to this instance, so
answer with "n":

.. image:: /_static/setup-guides/complete.png
  :width: 450
  :alt: Complete

The instance is now successfully configured and ready to accept UH VPN connections!

Step 4: Installing Client Apps
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This is the final step in the set up process. First login to the UH VPN `website`_ and navigate
to the group you created earlier. Now it's time to make a new person who's authorised to access
the VPN server you just created. Click the "Create New Person" button and the following
page will be presented:

.. image:: /_static/setup-guides/create-person.png
  :width: 600
  :alt: Create New Person

Enter your name and email address, then press submit and the person will then be created.

Next it's time to associate a device to the person that's just been created. To do so, click the
name of the person and then press the "Add new device" button and the following page
will be presented:

.. image:: /_static/setup-guides/create-device.png
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


.. _AWS: https://www.console.aws.amazon.com/
.. _website: https://uh-vpn.com
.. _create an account: https://uh-vpn.com/auth/signup
.. _Creating Groups: website/groups/creating.html
.. _server creation docs page: website/servers/creating.html
.. |key_icon| image:: /_static/icons/key.svg
  :alt: Key Icon
.. _device creation docs page: website/devices/creating.html
.. _clients docs page: clients/index.html