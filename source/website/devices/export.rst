Static Profile Export
=====================

UH VPN has the ability to export UH VPN device profiles in an OpenVPN compatible format to allow
administrators to cater for users running more exotic operating systems where UH VPN client
applications don't exist.

To export an OpenVPN profile click the |export_icon| icon next to the device in question. One will
then be presented with a modal prompt with two fields:

* **Server** : The server to link the static VPN profile to. Static profiles can't utilise multi-server
  selection and thus have to be bound to a single server. Select the appropriate one from the list.
* **Auto Add Credentials** : Certain OpenVPN applications permit credentials being auto-filled by
  the configuration profile, select this option if the client application supports this.

When the download button is pressed, a compressed zip file will be downloaded. Once extracted the file
structure is as follows:

* **README.txt** : Details instructions on how to import the VPN profile.
* **OpenVPN Profile** : OpenVPN config file to be utilised by an OpenVPN application. It is named to
  indicate the group, server, person and device in question.
* **credentials.txt** : File containing the username (first line) and password (second line) to use
  when prompted by OpenVPN for credentials.

.. |export_icon| image:: /_static/icons/cloud-download.svg
  :alt: Export Icon

.. warning::
    Only use this feature if absolutely necessary! Clients using these profiles will not benefit
    from dynamic secure updates, custom branding or enhanced performance. Use this feature at
    your own risk!
