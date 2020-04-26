Logging
=======

UH VPN Server software is built with various logging to aid users in diagnostic activities and to
provide telemetry data. All log files are stored in ``/var/log/uh-vpn-server/``.

Within the aforementioned directory there exists two file types:

1. **Daemon Log** : This provides information about the uh-vpn-server service. More specifically,
   information pertaining to tokens and configuration updates.
2. **VPN Log** : This provides information about specific VPN servers running on the host machine.

The daemon log file can be accessed at ``/var/log/uh-vpn-server/daemon.log`` and is limited to 4MB
in size. However, the file adopts a rotational backup policy such that when the file reaches 4MB in
size, the contents of this file is moved to ``/var/log/uh-vpn-server/daemon.log.1`` and the
``/var/log/uh-vpn-server/daemon.log`` is wiped to allow for fresh data to be recorded. This process
occurs twice meaning that a total of 12MB of log storage is permitted and three files are created,
namely ``daemon.log``, ``daemon.log.1`` and ``daemon.log.2`` with ``daemon.log`` containing the most
up to date logging information.

VPN log files adopt the naming policy of ``<token>.log`` where <token> is the associated API token
for the server in question. These log files are written directly from the underlying VPN core and
are useful in assisting with specific server problems.

.. tip::
    When reading these files it is recommended to use the commands ``less +G`` or ``tail`` to avoid
    polluting your terminal with endless log data!