Installation
============

UH VPN Server software demands the following prerequisites:

* **OS**: Ubuntu 20.04 (focal), 22.04 (jammy) or 24.04 (noble)
* **RAM**: 100MB (1GB preferable)
* **Network**: Machine accessible either by public IP address, hostname or dynamic DNS.

The first step is to install the required dependencies:

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install software-properties-common

Then it's time to add Ultra Horizon's package archive to the system sources:

.. code-block:: bash

    sudo add-apt-repository ppa:ultrahorizon/ppa

.. image:: /_static/setup-guides/ppa-confirm.png
  :width: 500
  :alt: PPA Confirm

A prompt will then display information about the repository, accept this, then download the package information
from this newly added archive:

.. code-block:: bash

    sudo apt-get update

Once this is done, UH VPN Server software can now be downloaded through the apt package manager.

.. code-block:: bash

    sudo apt-get install uh-vpn-server

Once installed check that the UH VPN Service is running:

.. code-block:: bash

    sudo service uh-vpn-server status

The output should say **active (running)** as depicted below:

.. image:: /_static/servers/service_status.png
  :width: 600
  :alt: Expected status

If one desires UH VPN Server to start at boot, issue the following command:

.. code-block:: bash

    sudo systemctl enable uh-vpn-server
