Installation
============

Upon downloading the MSI Installer, double click on it to install UH VPN.

You may recieve a "Windows protected your PC" SmartScreen warning when
launching the installer.  Click on "More Info" and then a "Run anyway" button
will appear allowing you to continue with the installation.

Verifying the Installer File (Advanced Users Only)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To verify the installer you can check the SHA256 hash with PowerShell.  Either
navigate to the file in PowerShell, or navigate to the file in Windows Explorer
and hold Shift and Right Click, and select "Open PowerShell window here".

Once in PowerShell and in the same folder as the MSI installer, run the following
command:

.. code-block:: bash

    Get-FileHash .\uh-vpn-installer_1.0.0.msi

The output should be as follows, pay close attention that the Hash is exactly
the same.

.. code-block:: bash

    Algorithm       Hash                                                                   Path
    ---------       ----                                                                   ----
    SHA256          32361FCCF91C9D491AD790011CBC529DEC39A0F33EF10B0862BF939A7C4C089A       uh-vpn-installer_1.0.0.msi


Alternatively, one can right click on the MSI in Windows File Exporer and select
"Properties".  In the properties dialog, select the "Digital Signatures"
tab, then "Details" for the signature, then "View Certificate".

In the Certificate dialog go to the "Details" tab, and find the
"Thumbprint".  It should match:

``ccaef34bfe6f8c8d180b240392487f4de45ed887``

If you have any further questions feel free to raise an issue on our [issue tracker](LINK).
