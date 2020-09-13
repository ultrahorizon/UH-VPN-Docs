Security
========

UH VPN utilises the latest standards in networking and cryptography and aims to be fully transparent
with respect to the protocols used. To that end, the list below itemises all the cryptographic mechanisms
used for each piece of infrastructure.

Website
~~~~~~~

* The website mandates HTTPS connections for all pages of the site and requires that TLS 1.2 be used.

API
~~~

* The API mandates HTTPS connections for all routes and requires that TLS 1.2 be used.
* Where infrastructure authentication is required (e.g. uh-vpn-server instances), a secret
  API token is used to provide access to a resource.
* Device profile synchronisation is handled by a proprietary one-time-code mechanism. A temporal
  nine digit code is exchanged for a JSON Web Token (JWT) which is signed by the UH VPN API.
  This JWT is stored within the device's secure enclave. Subsequent profile synchronisations
  utilise this JWT to gain access to a specific device profile.

VPN Tunnel
~~~~~~~~~~

The underlying protocol used within UH VPN is OpenVPN. The following security parameters are chosen:

* Each server is generated a unique 4096 bit RSA key signed by the UH VPN CA.
* AES-256-GCM is used as the data encryption algorithm.
* ECDHE is used for symmetric key exchange and uses curve secp384r1.
* TLS version 1.2 is mandated.
* Symmetric data encryption keys are exchanged and replaced every 30 minutes.
* Client authentication is handled by the UH VPN API and is performed over HTTPS.
