---
title: "About the ACCESS IdP"
---

Overview
--------
[ACCESS Operations](https://operations.access-ci.org/) operates an ACCESS InCommon Identity Provider (idp.access-ci.org) similar to the XSEDE InCommon Identity Provider (idp.xsede.org) that was previously operated by XSEDE Operations.
The ACCESS IdP:
* appears as "ACCESS CI (XSEDE)" in the list at cilogon.org, similar to how idp.xsede.org previously appeared as "XSEDE".
* uses the same usernames and passwords as idp.xsede.org and the same Duo MFA configuration.
* operates under the same [privacy](/privacy) and [security](/security) policies as idp.xsede.org.
* asserts eduPersonPrincipalName (ePPN) values of username@access-ci.org.

username@access-ci.org from idp.access-ci.org is the same person as username@xsede.org from idp.xsede.org (i.e., the same username@TERAGRID.ORG Kerberos principal).

For InCommon SAML SPs
---------------------
The SAML metadata for idp.access-ci.org is published by InCommon and can be
downloaded using the [Metadata Query (MDQ)
Service](https://spaces.at.internet2.edu/display/MDQ/production-metadata) from 
<https://mdq.incommon.org/entities/https%3A%2F%2Faccess-ci.org%2Fidp> .
Alternatively, you can download the metadata from <https://identity.access-ci.org/access-metadata.xml> and configure it in a local file.

For OIDC Clients
---------------------
Please see the [app registration] page for details on registering an OpenID Connect (OIDC) web application for ACCESS authentication.

Transition
----------
Applications previously relying on username@xsede.org values from idp.xsede.org should migrate to username@access-ci.org values from idp.access-ci.org.
