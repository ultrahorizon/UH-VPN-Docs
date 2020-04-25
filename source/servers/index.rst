*******
Servers
*******

UH VPN Server software runs on machines hosted by the end-user. This could be in a cloud or on-premise environment.
This software is responsible for the VPN link which encrypts and authenticates data between client applications
and the hosted machine running UH VPN Server software.

Configuration for UH VPN Servers is done via the `website`_ and each server created is assigned an API token, these
tokens are used by the server software to dynamically pull all configuration options from the UH VPN API. This
facilitatescentralised administration for VPN servers and greatly reduces the complexity involved in VPN deployment.

..  toctree::
    :maxdepth: 1

    installation
    adding-servers
    removing-servers
    upgrading
    logging

.. _website: https://uh-vpn.com