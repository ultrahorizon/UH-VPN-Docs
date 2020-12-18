Custom Cryptography (Enterprise Feature)
========================================

.. warning::
    Rolling your own crypto is dangerous. If you are at all unsure about what you are doing, use the cryptographic
    parameters provided to you automatically by UH VPN. Attempt this at your own risk!

There are certain circumstances where one may elect not to use the RSA keys and certificates issued by the UH VPN
certificate authority. For example, corporations often have their own PKI infrastructure already in place and as such
will elect to use their own cryptographic parameters.

In order to use custom cryptography, the following prerequisite objects must be obtained:

* **CA Certificate**: A public CA certificate under PEM encoding.
* **Server Certificate**: This is the public server certificate under PEM encoding which has been signed by the CA.
  This certificate must have "Digital Signing" and "Key Encipherment" privileges. It must also have "Server Authentication"
  defined as an extended key usage option.
* **Server Key**: This is the private key corresponding to the server certificate above. It must be PEM encoded and in
  PKCS #1 formatting.
* **Static TLS Key**: This is 256 random bytes of hex encapsulated by a header and trailer. It must have exactly 16 bytes
  per line (32 hex characters) and must include the standard OpenVPN static key header and trailer.

Once the parameters have been obtained, simply edit the relevant server within the appropriate group, switch on the
"Custom Cryptography" option and paste in the parameters into the corresponding fields. Once saved, connecting clients
and servers will communicate using your own custom defined cryptography options.



