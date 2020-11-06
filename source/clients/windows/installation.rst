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

.. code-block:: powershell

    Get-FileHash .\uh-vpn-installer_1.0.4.msi

The output should be as follows, pay close attention that the Hash is exactly
the same.

.. code-block:: none

    Algorithm       Hash                                                                   Path
    ---------       ----                                                                   ----
    SHA256          DCA433813F041B0F2E84D41CF1392DF548E8705549606CD52E93006EA34064F9       uh-vpn-installer_1.0.4.msi
    ... Older versions (for reference):
    SHA256          92D7BCE435987EFF7F266BC54A751E5443593FF036575931F5E69229432CBD08       uh-vpn-installer_1.0.3.msi
    SHA256          C85C9140B9598009D8B6DBC684247263BB8559B5A4079F476FC3B8E40BCDD648       uh-vpn-installer_1.0.2.msi
    SHA256          1FE952AE389CDEF4F430980C07C6FF29CA7CCD38CD80EF32E19717F2646AAE44       uh-vpn-installer_1.0.1.msi
    SHA256          32361FCCF91C9D491AD790011CBC529DEC39A0F33EF10B0862BF939A7C4C089A       uh-vpn-installer_1.0.0.msi


Alternatively, one can right click on the MSI in Windows File Exporer and select
"Properties".  In the properties dialog, select the "Digital Signatures"
tab, then "Details" for the signature, then "View Certificate".

In the Certificate dialog go to the "Details" tab, and find the
"Thumbprint".  It should match:

``ccaef34bfe6f8c8d180b240392487f4de45ed887``

If you have any further questions feel free to raise an issue on our `issue tracker`_.

.. _issue tracker: https://github.com/ultrahorizon/UH-VPN-Docs/issues/new/choose
