Removing VPN Servers
====================

Removing servers cannot be done whilst the uh-vpn-server service is running. The service needs to be stopped, then
the associated token removed from the token store in ``/etc/uh-vpn-server/tokens`` and then the service needs to be
restarted.

This operation has the side effect of halting all VPN servers configured on the host machine.

.. code-block:: bash

    $> sudo service uh-vpn-server stop

Now, the associated token needs to be removed from the token store:

.. code-block:: bash

    $> sudo nano /etc/uh-vpn-server/tokens

This will bring up an editor prompt like so:

.. image:: /_static/servers/token_store.png
  :width: 600
  :alt: Token store

Remove the token and save the file (Ctrl-X in nano). The service can then be restarted by issuing the command:

.. code-block:: bash

    $> sudo service uh-vpn-server start

One should then check that the service is up and running:

.. code-block:: bash

    $> sudo service uh-vpn-server status

The output should say **active (running)** as depicted below:

.. image:: /_static/servers/service_status.png
  :width: 600
  :alt: Expected status