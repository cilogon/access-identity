---
title: "FAQ"
---

# Frequently Asked Questions

![If you have XSEDE credentials and you are trying to log in to an ACCESS site, please choose ACCESS CI as your identity provider, and use your XSEDE credentials to log in.](/access-login-infographic.jpg)

# Users

1. Can I use my existing XSEDE account with ACCESS?
   - Yes, your ACCESS ID is the same as your XSEDE Portal account. Please do not create a
     new ACCESS ID. You do not need to change your password or your Duo registration
     during the transition from XSEDE to ACCESS.
1. Which identity provider should I choose when logging in?
   - Select the "ACCESS CI" identity provider to log in with your ACCESS/XSEDE username and password.
   - If you would like to log in to ACCESS using an identity provider other than "ACCESS CI", you need to link your identity from that other identity provider with your ACCESS ID. Please proceed to the [identity linking](/id-linking) page for details.
1. How do I log out?
   - Please visit <https://cilogon.org/logout> to log out of your CILogon session.
1. How do I clear or reset my CILogon browser cookies?
   - If you are having trouble logging in, it may help to click the "Delete ALL" button at <https://cilogon.org/me/> to reset your CILogon browser cookies, then try again to log in. 
1. How do I view information about my authenticated identity?
   - Visit [https://cilogon.org/me/](https://cilogon.org/me/?hide=browser,environment) to view the "Session Variables" associated with your authenticated identity, including your selected identity provider.
1. I forgot my ACCESS username. Can I get a reminder?
   - Yes, visit <https://identity.access-ci.org/username-reminder> to request a username reminder by email.
1. I forgot my ACCESS password. Can I reset it?
   - Yes, visit <https://identity.access-ci.org/password-reset> to reset your ACCESS password.
1. I'm having trouble with Duo. How do I update my Duo configuration?
   - Please visit <https://identity.access-ci.org/manage-mfa> for instructions on managing your Duo configuration for ACCESS.
1. Why doesn't my university appear in the list of identity providers?
   - ACCESS uses identity providers from CILogon. Please visit <https://www.cilogon.org/faq> for details.
1. How do I change the organization listed in my ACCESS profile?
   - Please [open a ticket](https://support.access-ci.org/open-a-ticket) to request the change.
1. I accidentially created multiple ACCESS IDs. Can I merge them?
   - Yes, please [open a ticket](https://support.access-ci.org/open-a-ticket) indicating which ACCESS ID you want to continue using and which one(s) you want marked as duplicate.
1. I'm having trouble logging in to an ACCESS Resource Provider. How can I get assistance?
   - Please review [ACCESS RP Documentation](https://access-ci.atlassian.net/wiki/x/HQmTB) for login details and support contacts for each resource provider.
   - If you're not able to get assistance directly from the resource provider, please [open a ticket](https://support.access-ci.org/open-a-ticket) with ACCESS.

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
