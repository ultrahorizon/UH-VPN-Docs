Upgrading
=========

Upgrading UH VPN Server software is simple and is done via the apt package manager on Ubuntu.
It is worth noting that this operation will restart all VPN servers in operation on the machine,
having the effect of disconnecting all connected clients which will then subsequently reconnect
after a period of around one minute.

The first step is to update the package archives:

.. code-block:: bash

    sudo apt-get update

To upgrade just UH VPN Server software issue the command:

.. code-block:: bash

    sudo apt-get install uh-vpn-server

This will install any updates for the uh-vpn-server service or alert you if you are already
on the latest version.

**Alternatively**, UH VPN Server software is also upgradeable via the command:

.. code-block:: bash

    sudo apt-get upgrade

However, doing so upgrades other packages already installed on the system.