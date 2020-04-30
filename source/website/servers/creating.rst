Creating Servers
================

Servers can be created by using the "Create New Server" button at the base of the list of servers on
the relevant group page. One will then be presented with a list of fields to fill in as follows:

* **Name** : Generic name for the server in question. E.g. Office UDP.
* **Appearance Order** : The order in which the server will appear in the list on client applications.
  0 = highest, ∞ = lowest.
* **Domain/IP Address** : The public IP address or hostname for the server.
* **Port** : IP port number for the server.
* **IPv4 Tunnel Network** : This is the IPv4 network that will be used for DHCP address assignment to UH VPN
  clients. This should be chosen such that it does not conflict with any subnets already defined on one's network.
* **IPv6 Tunnel Network** : This is the IPv6 network that will be used for DHCP address assignment to UH VPN
  clients. If you do not have an IPv6 public subnet, use fe80::/64, fe80:1::/64, fe80:2::/64 or similar
  to prevent IPv6 traffic from bypassing the VPN.
* **DNS Servers** : CSV list of DNS servers for UH VPN clients to use.
* **Add Forwarding Rule** : This will dynamically update Ubuntu's iptables to allow forwarding UH VPN traffic
  onto one's WAN interface. Only disable this when manually adding filter rules.
* **Add NAT Rule** : This will automatically insert a NAT rule in Ubuntu's iptables to allow UH VPN clients
  to access the IPv4 Internet from one's machine. Only disable this when manually adding NAT rules.

.. note::
    By default all UH VPN servers will push the routes 0.0.0.0/0 and ::/0 to redirect all IPv4 and IPv6
    traffic over the VPN interface.

Premium Server Options
~~~~~~~~~~~~~~~~~~~~~~

* **Redirect IPv4 Traffic** : This controls whether the 0.0.0.0/0 route is pushed to clients.

    * **Custom IPv4 Routes** : When the redirect button is disabled, one has the ability to insert
      custom IPv4 routes in CSV format. E.g. 192.168.0.0/24, 192.168.1.0/24.

* **Redirect IPv6 Traffic** : This controls whether the ::/0 route is pushed to clients.

    * **Custom IPv6 Routes** : When the redirect button is disabled, one has the ability to insert
      custom IPv6 routes in CSV format. E.g. fc00::/64, fc00:1::/64.

* **Custom Cryptography** : When selected, one is able to specify their own cryptographic parameters
  for use within UH VPN. Note this is only recommended if you are experienced in generating
  cryptographic keys and certificates. **Rolling your own crypto is dangerous!**.

Upon server submission, the above fields will be validated and submitted.