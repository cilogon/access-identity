---
title: "About the ACCESS IdP"
---

Overview
--------
[ACCESS Operations](https://operations.access-ci.org/) operates an ACCESS InCommon Identity Provider (idp.access-ci.org) similar to the XSEDE InCommon Identity Provider (idp.xsede.org) that was previously operated by XSEDE Operations.
The ACCESS IdP:
* appears as "ACCESS CI" in the list at cilogon.org, similar to how idp.xsede.org previously appeared as "XSEDE".
* uses the same usernames and passwords as idp.xsede.org and the same Duo MFA configuration.
* operates under the same [privacy](/privacy) and [security](/security) policies as idp.xsede.org.
* asserts eduPersonPrincipalName (ePPN) values of username@access-ci.org.

username@access-ci.org from idp.access-ci.org is the same person as username@xsede.org from idp.xsede.org (i.e., the same username@TERAGRID.ORG Kerberos principal).

Transition
----------
Applications previously relying on username@xsede.org values from idp.xsede.org should migrate to username@access-ci.org values from idp.access-ci.org.
