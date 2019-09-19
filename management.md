# Management Documentation

- [Overview](#overview)
- [Organisations](#organisations)
- [Servers](#servers)

## Overview

Authorised engineers are able to manage all aspects of their UH Enterprise installation at [https://uh-enterprise.com](https://uh-enterprise.com) from either a mobile or desktop. During installation of one's UH Enterprise infrastructure, relevant entities will be given account credentials and a tutorial for managing their deployment.

This documentation page serves as a reference manual for common operations engineers may wish to perform on their UH Enterprise infrastructure.

## Organisations

- [Admin Management](#admin-management)
- [Organisation Management](#organisation-management)

### Definition

UH Enterprise organisations represent a collective group personnel with access to a set of VPN servers. Every member registered in an organisation has access to all VPN servers defined within an organisation. Therefore, organisations should be constructed to reflect the relevant access permissions of users within a corporation.

### Admin Management

Every UH Enterprise organisation contains a list of administrators that are authorised to alter every part of an organisation including membership of other administrators. An admin can view the list of administrators at any point by clicking ![admins](https://uh-enterprise.com/static/images/icons/person.svg) next to any organisation one has access to.

#### Adding an admin

New admins can be enrolled by any organisation administrator by clicking the **Associate New Admin** button. Then one must enter the user ID of the new admin to associate them to the organisation in question. User ID's can be obtained from the [profile](https://uh-enterprise.com/profile) page in UH Enterprise.

#### Removing an admin

Existing admins can be removed at any time by clicking the ![admins](https://uh-enterprise.com/static/images/icons/trashcan.svg) next to an admin one wishes to remove. All access to the organisation for that admin will immediately be revoked.

### Organisation Management

Every UH Enterprise organisation has a set of associated properties which include:

- **Name:** The name of the organisation.
- **OTP Timeout:** Controls the expiry time of one time codes (seconds).
- **Logo:** Organisation logo for custom branding of mobile applications.
- **Primary Colour:** Primary colour used as the background colour in all mobile applications and email correspondence. The organisation logo will always be placed over this colour.
- **Secondary Colour:** Secondary colour used as the button colours in all mobile applications.

These properties are editable at any time by clicking ![edit](https://uh-enterprise.com/static/images/icons/pencil.svg) next to any organisation one has access to.


## Servers

- [Server Management](#server-management)

### Definition

Servers within UH Enterprise are remote access VPN servers that are specific to a UH Enterprise organisation. All identities and profiles within an organisation have access to these servers and can connect to them at any time.

### Server Management

Every UH Enterprise server has a set of associated properties which include:

- **Name:** The name of the server.
- **Domain/IP Address:** Location of the server on the Internet (e.g. gbr.uh-net.com or 1.2.3.4). For dual-stack servers create A and AAAA DNS records. UH Enterprise will then automatically use the correct IP protocol based on the client environment.
- **Port:** The logical IP port used for communication to the VPN server.
- **CA Certificate:** The CA certificate is the certificate of the entity which signed the UH Enterprise server's certificate.
- **Static TLS Key:** This is a 2048 bit static obfuscation key used to mask VPN traffic. This is **NOT** used for security purposes.
- **UDP Flag:** This sets the transport protocol to UDP or TCP based on the checkbox state.

These properties are editable at any time by clicking ![edit](https://uh-enterprise.com/static/images/icons/pencil.svg) next to any server one has access to. Changes to these options will then be dynamically pushed to UH Enterprise applications.

#### Creating a server

A server can be instantiated at any point by clicking the **Create New Server** button within any organisation one has access to. This will then prompt the admin to enter the details referenced in [Server Management](#server-management) above.

#### Deleting a server

Existing servers can be removed at any time by clicking the ![admins](https://uh-enterprise.com/static/images/icons/trashcan.svg) next to a server one wishes to remove. The server will be removed from all UH Enterprise profiles and the ability to select the server as a connection option in UH Enterprise applications will be removed.

