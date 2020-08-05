*****
Linux
*****

At present, UH VPN does not provide a Linux application, but will be releasing one by the end of 2020 targeted
at Ubuntu. In order to provide connectivity to Linux clients, a static profile must be `exported`_.

Before the profile can be used, one must install OpenVPN using their appropriate package manager. For example,
on Ubuntu the following commands would be executed:

.. code-block:: bash

    sudo apt-get update
    sudo apt-get install openvpn

Once OpenVPN has been installed and the UH VPN profile has been exported and is present on your local filesystem,
it can be utilised via executing the following command:

.. code-block:: bash

    sudo openvpn --config <profile>.ovpn

where ``<profile>`` is substituted for the filename of UH VPN profile. Note that the credentials must then
be supplied from the ``credentials.txt`` file supplied with the static profile.

.. note::
    One may wish to append the .ovpn profile with the ``up/down`` directives in order to execute commands
    upon connection or disconnection from the UH VPN server.

.. _exported: ../../website/devices/export.html
