---
title: "FAQ"
---

# Frequently Asked Questions

# Users

1. Can I use my existing XSEDE account with ACCESS?
   - Yes, your ACCESS ID is the same as your XSEDE Portal account. Please do not create a
     new ACCESS ID. You do not need to change your password or your Duo registration
     during the transition from XSEDE to ACCESS.
2. Which identity provider should I choose when logging in?
   - Select the "ACCESS CI" identity provider to log in with your ACCESS/XSEDE username and password.
   - If you would like to log in to ACCESS using an identity provider other than "ACCESS CI", you need to link your identity from that other identity provider with your ACCESS ID. Please proceed to the [identity linking](/id-linking) page for details.
3. How do I log out?
   - Please visit <https://cilogon.org/logout> to log out of your CILogon session.
4. How do I clear or reset my CILogon browser cookies?
   - If you are having trouble logging in, it may help to click the "Delete ALL" button at <https://cilogon.org/me/> to reset your CILogon browser cookies, then try again to log in. 
5. I forgot my ACCESS username. Can I get a reminder?
   - Yes, visit <https://identity.access-ci.org/username-reminder> to request a username reminder by email.
6. I forgot my ACCESS password. Can I reset it?
   - Yes, visit <https://identity.access-ci.org/password-reset> to reset your ACCESS password.
7. I'm having trouble with Duo. How do I update my Duo configuration?
   - Please visit <https://identity.access-ci.org/manage-mfa> for instructions on managing your Duo configuration for ACCESS.
8. Why doesn't my university appear in the list of identity providers?
   - ACCESS uses identity providers from CILogon. Please visit <https://www.cilogon.org/faq> for details.

# Admins

1. Can I configure my web application to require authentication using the
   [ACCESS CI Identity Provider (IdP)](/about-access-idp)?
   - By default, when you [register your web application](/register-app), ACCESS users
     will be able to log in using any identity provider supported by CILogon that is
     linked to their ACCESS ID, and the resulting id\_token will contain the user's ACCESS
     ID (i.e., "sub": "username@access-ci.org"). This is the recommended configuration,
     because it allows users to log in without needing an ACCESS-specific username and
     password.
   - However, if you want to require authentication using the ACCESS CI IdP (e.g., to
     require ACCESS multi-factor authentication), please contact
     [help@cilogon.org](mailto:help@cilogon.org) to request this configuration to be
     applied to your client. Include your registered client\_id in your request.
1. What is the ACCESS "Named Configuration"?
   - When you register an OIDC client with the ACCESS COmanage Registry, is it recommended
     you use a Named Configuraton for "ACCESS OIDC client configuration v1". This
     configuration does the following:
     - Registers the following [scopes](https://www.cilogon.org/oidc#h.p_PEQXL8QUjsQm):
       openid, email, profile, org.cilogon.userinfo 
     - Verifies that OIDC client transactions request the org.cilogon.userinfo scope
     - Checks that the user has an ACCESS account. If so, asserts
       "username@access-ci.org" in the "sub" claim. If not, redirects the user to
       an appropriate error page.
     - Checks if the user is in the "AccessDenied" group. If so, redirects the user to an
       appropriate error page.
1. Why does my OIDC client not show the ACCESS "skin" (i.e., CSS) when authenticating?
   - There is a server-side configuration which automatically applies the
     [ACCESS skin](https://cilogon.org/?skin=access) for OIDC clients with a
     redirect_uri in the access-ci.org domain. This skin changes the CSS for the "Select
     an Identity Provider" page, and also selects "ACCESS CI" as the initial IdP for new
     visitors to the site. However, your OIDC client might have a redirect_uri in some
     other domain. In this case, the ACCESS "skin" would not be applied. To fix this,
     please contact [help@cilogon.org](mailto:help@cilogon.org) with your registered
     client\_id and request that the ACCESS "skin" be applied to your client.
1. Can I get a mapping from CILogon DNs to ePPN values to help with the GCSv4 to GCSv5
   transition?
   - Yes, please send a list of DNs to [help@cilogon.org](mailto:help@cilogon.org), and
     the CILogon team can provide the mapping.
1. Why does my OIDC client require users to re-authenticate so frequently?
   - If you are using [mod_auth_openidc](https://github.com/zmartzone/mod_auth_openidc), please be sure to configure OIDCSessionInactivityTimeout. Visit <https://www.cilogon.org/oidc#h.p_1_IG_eaP90Ty> for details.
   - You may also need to enable Refresh Tokens in your [web app registration](/register-app).
