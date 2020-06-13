*******
Servers
*******

UH VPN servers are managed through the `website`_ and are contained within UH VPN groups. Every server
defined within a group permits access from all persons within that group. This facilitates
a simple authentication structure.

All VPN configuration options such as transport protocol, port, IP routing, cryptography and so on is
specififed through the management interface and this information is dynamically pushed every minute to
UH VPN Server software to allow for dynamic configuration updates and reduced complexity in server
configuration.

..  toctree::
    :maxdepth: 1

    creating
    editing
    deleting
    api-tokens

Advanced server tutorials
~~~~~~~~~~~~~~~~~~~~~~~~~

..  toctree::
    :maxdepth: 1

    dualstack
    custom-crypto
    split-routing

.. _website: https://uh-vpn.com