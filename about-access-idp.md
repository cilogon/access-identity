---
title: "About the ACCESS IdP"
---

Timeline
--------
* August 1 2022: The ACCESS IdP is pre-production, using pre-production APIs and pre-production user data. The IdP is registered with CILogon and Globus but registration with InCommon is still in progress.
* August 23 2022: The ACCESS IdP will begin production operation.

Overview
--------
[ACCESS Operations](https://operations.access-ci.org/) operates an ACCESS InCommon Identity Provider (idp.access-ci.org) similar to the XSEDE InCommon Identity Provider (idp.xsede.org).
The ACCESS IdP:
* appears as "ACCESS CI" in the list at cilogon.org, similar to how idp.xsede.org appears as "XSEDE".
* uses the same usernames and passwords as idp.xsede.org and the same Duo MFA configuration.
* operates under the same [privacy](/privacy) and [security](/security) policies as idp.xsede.org.
* asserts eduPersonPrincipalName (ePPN) values of username@access-ci.org.

username@access-ci.org from idp.access-ci.org is the same person as username@xsede.org from idp.xsede.org (i.e., the same username@TERAGRID.ORG Kerberos principal).

Transition
----------
Applications (such as Globus) currently relying on username@xsede.org values from idp.xsede.org will need to migrate to username@access-ci.org values from idp.access-ci.org.
CILogon can provide ID Tokens containing username@access-ci.org and/or username@xsede.org values on a per-application basis as needed to support a smooth transition for applications. Contact [help@cilogon.org](mailto:help@cilogon.org) to request a custom configuration. Include your client_id in the request.
