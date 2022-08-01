---
title: "Register a web application for ACCESS authentication"
---

Temporary Manual Process
------------------------
Until the ACCESS COmanage web interface for OpenID Connect web application registration is ready, please use the following manual process.

1. Submit the form at https://cilogon.org/oauth2/register to register your web application. Record the client_id and client_secret values.
2. Send email using the following template (replacing CLIENTID with the client_id value you received from the registration form):
```
To: [help@cilogon.org](mailto:help@cilogon.org)
Subject: ACCESS configuration for CLIENTID

Please configure CLIENTID to set the sub claim to the user's ACCESS ID instead of the default CILogon ID.
```
3. To later update your client configuration or for any additional assistance, please contact [help@cilogon.org](mailto:help@cilogon.org).

COmanage Web Interface
----------------------
We are configuring ACCESS COmanage to support OpenID Connect web application registration and management.
Please use the manual process above until the COmanage configuration is ready.

References
----------
See <https://www.cilogon.org/oidc> for details on CILogon's support for OpenID Connect applications.
