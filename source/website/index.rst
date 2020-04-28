*******
Website
*******

The UH VPN `website`_ acts as the command and control centre for all UH VPN deployments.
UH VPN clients and servers rely on the availability of this site to provide functionality
such as network authentication, configuration updates and much more. Every time a change is
made on the website, this change is securely pushed to all relevant UH VPN clients and
servers. This removes the need for administrators to ship new VPN profiles to clients
and install new cryptographic keys for servers, instead this can all be done securely,
quickly and easily through the simple to use web interface without any extra intervention
required from end-users of the service.

The overarching structure of the management interface within the website is based around
the following concept:

**Groups** of **people** own **devices** which authenticate onto **servers**.

This is the simplest explanation for the inspiration behind the interface structure and
further explanations for each of these terms is detailed below.

..  toctree::
    :maxdepth: 2

    groups/index
    servers/index
    people/index
    devices/index


.. _website: https://uh-vpn.com