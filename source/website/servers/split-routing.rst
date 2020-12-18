Split Routing (Enterprise Feature)
==================================

Split routing is often used where it is not desirable to route your entire Internet connection over the VPN tunnel.
For example, you may wish to utilise your standard Internet connection for general browsing whilst having UH VPN to
facilitate access to an office network.

In the example below we will configure UH VPN to only route traffic destined for ``192.168.0.0/24`` over the VPN.

First head over to the `website`_ and within the appropriate group, edit the relevant server and switch off
"Redirect all IPv4 traffic" and "Redirect all IPv6 traffic" as shown below:

.. image:: /_static/website/servers/custom-routes.png
  :width: 600
  :alt: Custom Routing

This will display the custom route fields for both IPv4 and IPv4. Update the fields to the following:

- **Custom IPv4 Routes** : ``192.168.0.0/24``
- **Custom IPv6 Routes** : Leave blank

This will ensure connecting clients are pushed only a route for the ``192.168.0.0/24`` subnet.
Update the subnet values to match your particular configuration.

.. tip::
    The same procedure can be adapted to IPv6 networks by specifying a custom IPv6 subnet in the "Custom IPv6 Routes"
    field.

.. _website: https://uh-vpn.com