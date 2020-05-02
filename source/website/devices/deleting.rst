Revoking Devices
================

UH VPN supports instant device revocation to aid situations where devices need to be revoked prior
to their expiry date. To do so, administrators simply need to click the |delete_icon| icon next
to the device in question. Once a device is deleted it cannot be undone and all authentications
for the device in question will immediately fail. Moreover, dynamic configuration updates for the
device profile will also fail and the end user will be informed of revocation by their UH VPN
client application.

.. |delete_icon| image:: /_static/icons/trashcan.svg
  :alt: Delete Icon