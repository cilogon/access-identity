---
title: "FAQ"
---

# Frequently Asked Questions

## Users

1. Can I use my existing XSEDE account with ACCESS?
   - Yes, your ACCESS account is the same as your XSEDE Portal account. Please do not create a new ACCESS account. You do not need to change your password or your Duo registration during the transition from XSEDE to ACCESS.

## Admins

1. Can I configure my web application to require authentication using the [ACCESS IdP](/about-access-idp)?
   - By default, when you [register your web application](/register-app), ACCESS users will be able to log in using any identity provider supported by CILogon that is linked to their ACCESS ID, and the resulting id_token will contain the user's ACCESS ID (i.e., "sub": "username@access-ci.org"). This is the recommended configuration, because it allows users to log in without needing an ACCESS-specific username and password.
   - However, if you want to require authentication using the ACCESS IdP (e.g., to require ACCESS multi-factor authentication), please contact [help@cilogon.org](mailto:help@cilogon.org) for assistance. Include your registered client_id in your request.
