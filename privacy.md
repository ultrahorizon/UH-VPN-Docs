# UH Enterprise Privacy Policy

Ultra Horizon is committed to protecting your privacy. We want you to understand what information we collect, what we don’t collect, and how we collect, use, and store information. 

**We do not collect logs relating to the organisation or users activity, including no logging of browsing history, traffic destination, data content, or DNS queries. We also never store connection logs, meaning no logs of your IP address, your outgoing UH Enterprise IP address, connection timestamp, or session duration.** This is fundamentally because the servers operating behind UH Enterprise are owned and controlled by user or organisation paying for the service.

Our guiding principle towards data collection is to only collect the minimal data required to operate a world-class secure network authorisation service at scale. We designed our systems to not have sensitive data about our customers; even when compelled we cannot provide data that we do not possess.

This privacy policy will help you understand how Ultra Horizon Ltd. collects, uses, and stores information.

## Parties

In this privacy policy (up to and past this section), Ultra Horizon Ltd. will be referred to as “**Ultra Horizon**”, or the English first person plural: “**we**”, “**us**”, “**our**”, "**ours**", or "**ourselves**"

UH Enterprise is a service that is provided to third party entities, which will be referred to as the "**entity**", "**organisation**", "**enterprise**", or (unless otherwise specified) English third person plural: "**they**", "**them**", "**their**", "**theirs**", or "**themselves**".

The service provided by UH Enterprise to the organisation is for use by whoever they wish be it clients, employees or other relations.  These users will be referred to as the **users**, or (unless otherwise specified) English second person plural: "**you**", "**your**", "**yours**", or "**yourselves**".

## Table of contents

- [Information stored about the Organisation](#information-stored-about-the-organisation)
- [Information stored about the users](#information-stored-about-the-users)
- [Aggregate information stored](#aggregate-information-stored)
- [Information Related to Email Support](#information-related-to-email-support)
- [VPN Tunnel Monitoring](#vpn-tunnel-monitoring)
- [Jurisdiction and Applicable Law](#jurisdiction-and-applicable-law)
- [Security Measures](#security-measures)
- [Third-party Websites](#third-party-websites)
- [Consent and Age Restrictions](#consent-and-age-restrictions)
- [Changes to the Privacy Policy](#changes-to-the-privacy-policy)
- [Contacting Ultra Horizon](#contacting-ultra-horizon)


## [Information stored about the organisation](#table-of-contents)

This section is only applicable to the organisation and administrators making use of the management interface at [https://uh-enterprise.com](https://uh-enterprise.com).  In this section, the second person plural ("**you**", "**your**", "**yours**", or "**yourselves**") refers to the individual account holders on management interface.

Information is collected for the purpose of administering the UH Enterprise subscription owned by the entity, and includes your name and email address which you submit when you sign up for our Services.  This information is stored by our third party authentication provider, Auth0.  All interactions with Auth0 are done over encrypted connections.

Information stored about the entity is for the purpose of maintaining the core UH Enterprise service, and includes the name, logo, one-time password expiry time and colour choices of the organisation.

In addition to this, critical information to facilitate VPN connections to servers hosted by the entity are stored, including a name, domain/IP address, port number, CA certificate, static TLS Key and transport protocol. 

Finally, information pertaining to abstract identities and profiles are kept by us.  Information related to the identity includes a string that represents a name for the identity, along with an email address to deliver one-time passwords to.  Information related to the profile includes a string that represents the name of the profile, along with an optional expiry time for the profile.  After generation of a profile and until consumption, a one-time password that is associated with an organisation, identity and profile is also stored.

## [Information stored about the users](#table-of-contents)

This section is only applicable to the users of the UH Enterprise native applications, be it on any mobile or desktop platform, and marks the return of the second person plural ("**you**", "**your**", "**yours**", or "**yourselves**") referring to the users.

The users are provided with a one-time password to their email address by the organisation when assigned a profile.  The organisation will have specified an identifier for them which may or may not be their name, along with an identifier for the device that the one-time password is entered on.  Once consumed, this one-time password is removed from the server and the profile is synced by use of a cryptographically signed token stored only on the users device.

No information is collected by Ultra Horizon about the app users.

After a profile is synced, the secure token is used to request from Ultra Horizon any updates pertaining to the profile, including revocation and server changes.  All other interactions are then solely through the VPN connection directly to the organisation's servers.

## [Aggregate information stored](#table-of-contents)

Ultra Horizon collects minimal information about usage in order to maintain excellent customer support and quality of service. The section below describes in detail what specific information we collect. These statistics never include anything about what the user has done with the secure network connection: no data about the contents or destinations of traffic, no DNS queries, and no IP addresses.

For users of our VPN applications, we collect practically no metadata on usage. Similarly, for management users we only store a name and email address to allow unique identification of a UH Enterprise subscription.

We’ve engineered our systems to categorically eliminate storage of sensitive data. We stand by our firm commitment to our customers’ privacy by not possessing any data related to a user’s online activities.

### App Data Collection

We do not add any of our own telemetry or tracking to any UH Enterprise web or native apps.  Telemetry information including but not limited to installation/reviews/crash reports may be collected out of our control by third party app distribution platforms or operating systems.

In the rare event that you experience a problem with a native UH Enterprise app, you may be asked if you wish to submit a bug report automatically which will send you to a pre-populated report on our [issue tracker](https://github.com/ultrahorizon/UH-Enterprise-Docs/issues/), provided by GitHub. Pre-populated reports contain information about the platform that the app is on, the time of the crash, along with minimal critical debugging information that will allow us to identify the issue quickly.  No reports are ever sent automatically, and you can preview all information before it is sent.

### Connection Statistics

We ensure that we never log browsing history, traffic destination, data content, IP addresses, or DNS queries. Therefore:

 - We do not know whether a user ever accessed a particular website or service.
 - We do not know which user was connected to the secure network at a specific time or which UH Enterprise server IP addresses they used.
 - We do not know the set of original IP addresses of a user’s computer.

Should anyone try to compel Ultra Horizon to release retrospective user information based on any of the above, **we cannot supply this information because the data doesn’t exist.**

## [Information Related to Email Support](#table-of-contents)

In this section, the second person plural ("**you**", "**your**", "**yours**", or "**yourselves**") refers to the individual account holders on management interface.

Ultra Horizon keeps records of any correspondence, questions, complaints, or compliments you submit to us through our Site or Services, along with our response. Depending on how you contact Ultra Horizon, we may collect any information that is listed on your account and any subsequent information you provide to us. Having full correspondence records enables our staff to provide the best possible customer support experience.

We use one third-party platform for email support correspondence: Intercom (for the remainder of this section referred to as the English third person plural: "**they**", "**them**", "**their**", "**theirs**", or "**themselves**"). When you correspond with us using this platform, your correspondence records, including your name, email address, are stored in their systems. The platform utilises modern security practices and all our live chats are encrypted.

## [VPN Tunnel Monitoring](#table-of-contents)

Ultra Horizon does not monitor or log any traffic being sent over the VPN tunnel.  The only time Ultra Horizon has knowledge of information regarding a connection is to authenticate users logging into a server operated by an organisation.  These authentications are logged and submitted to the UH Enterprise management interface.

Once connected, the secure VPN tunnel is direct from the organisation's server to the user.  We do not have any access to the connections, nor can offer any guarantee about what happens to data upon arriving at the organisation.  Users should be familiar with an organisation and their operating procedures/privacy policy and associated terms of service where applicable.

## [Jurisdiction and Applicable Law](#table-of-contents)

Ultra Horizon’s core mission is to keep your information private. We are a registered company in the United Kingdom.

Should we receive a valid legal order from the United Kingdom High Court to release information pertaining to a user, it is important to note that **Ultra Horizon does not collect any IP addresses, browsing history, encryption keys, traffic data, or DNS queries that could be used to identify any specific user.**

## [Security Measures](#table-of-contents)

Ultra Horizon uses best-in-class physical, procedural, and technical security with respect to our offices and information storage facilities so as to prevent any loss, misuse, unauthorised access, disclosure, or modification of information. Access to user information is restricted to staff who require such access to perform their job functions.

Any servers provided by Ultra Horizon for use as endpoints by organisations are designed to these same standards, but may not be managed by Ultra Horizon.

Any profiles stored on a user's device are also encrypted and stored in the best means possible for the respective platform.

While we believe these systems are robust, it is important to understand that no data security measures in the world can offer 100% protection.

Even if a government were to physically seize a server, UH Enterprise endpoint, or user's device from us, the organisation or a user, there would be no logs or information that would tie any individual user to a particular event, website, or behaviour.

## [Third-party Websites](#table-of-contents)

The websites operated by Ultra Horizon may contain links to external websites that do not fall under Ultra Horizon’s domain. Ultra Horizon is not responsible for the privacy practices or content of such external websites.

## [Consent and Age Restrictions](#table-of-contents)

By using the Website, Content, Apps, Software, or Services, you agree to have your information handled as described in our [Terms of Service](/terms) and this Privacy Policy.

The Services are intended for adults aged 18 and above. If you believe your child has provided information to us, please let us know immediately.

## [Changes to the Privacy Policy](#table-of-contents)

We may change our Privacy Policy from time to time, without prior notice to you, consistent with applicable privacy laws and principles. Your continued use of the Website or Services constitutes your acceptance of our Privacy Policy.

## [Contacting Ultra Horizon](#table-of-contents)

If you have any questions regarding our Privacy Policy and how we handle your information, please feel free to contact Ultra Horizon on the [contact page](https://ultra-horizon.com/contact) of the website or get in touch via [enquiries@ultra-horizon.com](mailto:enquiries@ultra-horizon.com).