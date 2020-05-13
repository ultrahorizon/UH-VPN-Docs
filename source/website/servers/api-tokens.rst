Obtaining API Tokens
====================

To use a server defined on the `website`_ with UH VPN Server software it is necessary to obtain an
API token for the server in question. To do this one needs to click the |key_icon| icon next to the
appropriate server in the list of servers on the relevant group page. After clicking, one will
be presented with a modal as shown below:

.. image:: /_static/website/servers/token.png
  :width: 400
  :alt: Token Modal

One simply needs to copy the token (shown in pink) and either follow:

- `UH VPN Setup Script`_ available if using our `Digital Ocean Image`_
- `Adding servers`_ instructions in order to link the server software with the UH VPN API
  if using a vanilla Ubuntu installation.

If a token has been compromised, the "Regenerate" button can be used to create a new token for the
server in question. **This will instantly revoke the old API token**

.. |key_icon| image:: /_static/icons/key.svg
  :alt: Key Icon

.. _website: https://uh-vpn.com
.. _UH VPN Setup Script: ../../simple-setup.html#step-3-configuring-the-droplet
.. _Digital Ocean Image: https://marketplace.digitalocean.com/apps/uh-vpn
.. _adding servers: ../../servers/adding-servers.html