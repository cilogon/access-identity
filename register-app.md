---
title: "Register a Web App for ACCESS Auth"
---

COmanage Web Interface
----------------------
ACCESS uses CILogon COmanage for OpenID Connect (OIDC) web
application registration and management.
Please contact [help@cilogon.org](mailto:help@cilogon.org)
(**Subject**: ACCESS OIDC client management) to request an invitation.
In your email message, please specify your ACCESS affiliation:
* RAMPS (Track 1)
* MATCH (Track 2)
* CONECT (Track 3)
* MMS (Track 4)
* OpenCI (ACO)
* Service Provider

You will receive an email with a link to register for CILogon COmanage.
During the enrollment flow, we suggest you authenticate with your
institutional/university identity provider (IdP) rather than the ACCESS CI
IdP.

After you have registered with CILogon COmanage, see [COmanage
OIDC Clients](https://www.cilogon.org/comanage/oidc-clients) for
information on registering and managing OIDC clients.

When registering your client, we recommend selecting "Use a Named Configuration" then choosing "ACCESS OIDC client configuration v1".
This configuration causes the ACCESS ID with @access-ci.org to be returned as the OIDC sub claim in the id_token.
To use this configuration, be sure to configure your client to request the following scopes: openid, email, profile, org.cilogon.userinfo

References
----------
See <https://identity.access-ci.org/devguide> for developer recommendations when integrating with ACCESS identity management services.

See <https://www.cilogon.org/oidc> for details on CILogon's support for OpenID Connect applications.

See <https://www.cilogon.org/comanage/oidc-clients> for
information about CILogon COmanage OpenID Connect (OIDC) clients.

See <https://identity.access-ci.org/about-access-idp> for information about using the ACCESS IdP for authentication.
