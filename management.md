# Management Documentation

- [Overview](#overview)
- [Organisations](#organisations)
- [Servers](#servers)
- [Identities](#identities)
- [Profiles](#profiles)

## [Overview](#management-documentation)

Authorised engineers are able to manage all aspects of their installation on the UH Enterprise [web interface](https://uh-enterprise.com) from either a mobile or desktop computer. During installation of one's UH Enterprise infrastructure, relevant entities will be given account credentials and a tutorial for managing their deployment.

This documentation page serves as a reference manual for common operations engineers may wish to perform on their UH Enterprise infrastructure.

## [Organisations](#management-documentation)

- [Admin Management](#admin-management)
	- [Creating an admin](#creating-an-admin)
	- [Deleting an admin](#deleting-an-admin)
- [Organisation Management](#organisation-management)
	- [Creating an organisation](#creating-an-organisation)
	- [Deleting an organisation](#deleting-an-organisation)

### Definition

UH Enterprise organisations represent a collective group of personnel with access to a set of VPN servers. Every member registered in an organisation has access to all VPN servers defined within an organisation. Therefore, organisations should be constructed to reflect the relevant access permissions of users within a corporation.

### [Admin Management](#organisations)

Every UH Enterprise organisation contains a list of administrators that are authorised to alter every part of an organisation including membership of other administrators. An admin can view the list of administrators at any point by clicking ![admins](https://uh-enterprise.com/static/images/icons/person.svg) next to any organisation one has access to.

#### [Creating an admin](#organisations)

New admins can be enrolled by any organisation administrator by clicking the **Associate New Admin** button. Then one must enter the user ID of the new admin to associate them to the organisation in question. User ID's can be obtained from the [profile](https://uh-enterprise.com/profile) page in UH Enterprise.

#### [Deleting an admin](#organisations)

Existing admins can be deleted at any time by clicking the ![admins](https://uh-enterprise.com/static/images/icons/trashcan.svg) next to an admin one wishes to remove. All access to the organisation for that admin will immediately be revoked.

### [Organisation Management](#organisations)

Every UH Enterprise organisation has a set of associated properties which include:

- **Name:** The name of the organisation.
- **OTP Timeout:** Controls the expiry time of one time codes (seconds).
- **Logo:** Organisation logo for custom branding of mobile applications.
- **Primary Colour:** Primary colour used as the background colour in all mobile applications and email correspondence. The organisation logo will always be placed over this colour.
- **Secondary Colour:** Secondary colour used as the button colours in all mobile applications.

These properties are editable at any time by clicking ![edit](https://uh-enterprise.com/static/images/icons/pencil.svg) next to any organisation one has access to. Changes to these options will then be dynamically pushed to UH Enterprise applications.

#### [Creating an organisation](#organisations)

An organisation can only be instantiated if one has been given the UH Enterprise global `admin` scope by Ultra Horizon. If this has been given, a user can create an organisation at any point by clicking the **Create New Organisation** button on the [remote access](https://uh-enterprise.com/remote-access) page.

#### [Deleting an organisation](#organisations)

Existing organisations can be deleted at any time by clicking the ![admins](https://uh-enterprise.com/static/images/icons/trashcan.svg) next to an organisation one wishes to remove. **The entire organisation will be removed including all servers, identities and profiles**. This is a non-recoverable action.


## [Servers](#management-documentation)

- [Server Management](#server-management)
	- [Creating a server](#creating-a-server)
	- [Deleting a server](#deleting-a-server)

### Definition

Servers within UH Enterprise are remote access VPN servers that are specific to a UH Enterprise organisation. All identities and profiles within an organisation have access to these servers and can connect to them at any time.

### [Server Management](#servers)

Every UH Enterprise server has a set of associated properties which include:

- **Name:** The name of the server.
- **Domain/IP Address:** Location of the server on the Internet (e.g. gbr.uh-net.com or 1.2.3.4). For dual-stack servers create A and AAAA DNS records. UH Enterprise will then automatically use the correct IP version based on the client environment.
- **Port:** The logical IP port used for communication to the VPN server.
- **CA Certificate:** The CA certificate is the certificate of the entity which signed the UH Enterprise server's certificate.
- **Static TLS Key:** This is a 2048 bit static obfuscation key used to mask VPN traffic. This is **NOT** used for security purposes.
- **UDP Flag:** This sets the transport protocol to UDP or TCP based on the checkbox state.

These properties are editable at any time by clicking ![edit](https://uh-enterprise.com/static/images/icons/pencil.svg) next to any server one has access to. Changes to these options will then be dynamically pushed to UH Enterprise applications.

#### [Creating a server](#servers)

A server can be instantiated at any point by clicking the **Create New Server** button within any organisation one has access to. This will then prompt the admin to enter the details referenced in [Server Management](#server-management) above.

#### [Deleting a server](#servers)

Existing servers can be deleted at any time by clicking the ![admins](https://uh-enterprise.com/static/images/icons/trashcan.svg) next to a server one wishes to remove. The server will be removed from all UH Enterprise profiles and the ability to select the server as a connection option in UH Enterprise applications will be removed.

## [Identities](#management-documentation)

- [Identity Management](#identity-management)
	- [Creating an identity](#creating-an-identity)
	- [Deleting an identity](#deleting-an-identity)

### Definition

UH Enterprise identities represent authorised personnel within an organisation. These identities can be thought of as any entity who is authorised to connect to  the organisation's servers.

### [Identity Management](#identities)

Every UH Enterprise identity has a set of associated properties which include:

- **Name:** The name of the identity.
- **Email:** The email address for the identity. 

These properties are editable at any time by clicking ![edit](https://uh-enterprise.com/static/images/icons/pencil.svg) next to any server one has access to. Changes to these options will then be dynamically pushed to UH Enterprise applications.

#### [Creating an identity](#identities)

An identity can be instantiated at any point by clicking the **Create New Identity** button within any organisation one has access to. This will then prompt the admin to enter the details referenced in [Identity Management](#identity-management) above.

#### [Deleting an identity](#identities)

Existing identities can be deleted at any time by clicking the ![admins](https://uh-enterprise.com/static/images/icons/trashcan.svg) next to an identity one wishes to remove. The identity will be removed and all profiles within the identity will be deleted, revoking all access to the organisation's servers for the affected profiles.


## [Profiles](#management-documentation)

- [Profile Management](#profile-management)
	- [Creating a profile](#creating-a-profile)
	- [Deleting a profile](#deleting-a-profile)
	- [Exporting a profile](#exporting-a-profile)

### Definition

UH Enterprise profiles represent devices belonging to identities defined within an organisation. As such, profiles are immutable objects which grant access to an organisation's server and the deletion of a profile immediately revokes access to all organisation servers for that device.

### [Profile Management](#profiles)

Every UH Enterprise profile has a set of associated properties which include:

- **Name:** The name of the profile which should reflect the type of device the profile is intended for (e.g. iPhone).
- **Expiry Date:** The time at which the profile will be revoked by UH Enterprise servers and access to servers will no longer be permitted. This can be set to any date. Alternatively, this field can be left blank to generate a profile without an expiry date. 

Profiles are immutable one-time objects. They cannot be altered once created. If alternations must be made, the profile must be deleted and a replacement created instead.

#### [Creating a profile](#profiles)

A profile can be instantiated at any point by clicking the **Create New Profile** button under any identity within an organisation one has access to. This will then prompt the admin to enter the details referenced in [Profile Management](#profile-management) above.

#### [Deleting a profile](#profiles)

Existing profiles can be deleted at any time by clicking the ![admins](https://uh-enterprise.com/static/images/icons/trashcan.svg) next to a profile one wishes to remove. The profile will be removed and access to all organisation servers for that device will immediately be revoked.

#### [Exporting a profile](#profiles)

In the case that one wishes to export a profile for a more exotic operating system where UH Enterprise applications have not yet been ported, UH Enterprise offers a static export facility compatible with regular OpenVPN clients. By clicking the ![export](https://uh-enterprise.com/static/images/icons/cloud-download.svg) icon a prompt will appear enabling an admin to build a static profile for download. The admin can choose a server and whether to auto-add credentials into the profile. If the **Download** button is pressed a `zip` file is generated containing the newly generated static profile. Within this `zip` file is `README.txt` which explains how to set up the static profile on standard OpenVPN clients.
