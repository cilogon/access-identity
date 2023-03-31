---
title: "Manage Multi-Factor Authentication"
---

ACCESS uses Duo for Multi-Factor Authentication (MFA).

Please see <https://guide.duo.com/universal-prompt> for details about managing your Duo MFA options using the Duo Universal Prompt.

To add additional verification methods or manage your existing devices, please see <https://guide.duo.com/universal-prompt#add-or-manage-devices>.

## Initial Enrollment in Duo for ACCESS

To enroll with Duo for ACCESS:

1. Visit <https://cilogon.org/me/> and click the "Delete ALL" button.
2. Visit <https://registry.access-ci.org/registry/auth/logout> and click the "LOGIN" button.
3. In the "Select an Identity Provider" box, choose "ACCESS CI (XSEDE)" and click the "Log On" button.
4. Enter your ACCESS username and password on the idp.access-ci.org login page. (To set/reset your ACCESS password, visit <https://identity.access-ci.org/password-reset>.)
5. You will be prompted to enroll in Duo. [Install the Duo security app](https://duo.com/product/multi-factor-authentication-mfa/duo-mobile-app#download) on your phone and configure it to use "[Duo Push](https://guide.duo.com/universal-prompt#duo-push)".
6. You should see the "ACCESS User Identity Dashboard".

Now you should be able to log in to any other ACCESS website such as [ACCESS Allocations](https://allocations.access-ci.org/).

## Manage (Add/Delete) Devices used by Duo for ACCESS

To re-visit the Duo Universal Prompt to manage your devices after logging in:

1. Open a private browser window in [Chrome](https://support.google.com/chrome/answer/95464), [Firefox](https://support.mozilla.org/en-US/kb/private-browsing-use-firefox-without-history), [Safari](https://support.apple.com/guide/safari/browse-privately-ibrw1069/mac), or your preferred web browser. Using a private browser window ensures that Duo will display the Universal Prompt even if you have previously logged in.
2. Visit <https://cilogon.org/?selected_idp=https%3A%2F%2Faccess-ci.org%2Fidp&skin=access> to log in using the ACCESS IdP.
3. Click the "Log On" button.
4. Enter your ACCESS username and password on the idp.access-ci.org login page.
5. Click "Other options" on the duosecurity.com page.
6. Click "Manage devices" on the duosecurity.com page.
7. Use an existing method to log in to Duo.
8. Use the device management page to manage your devices.
9. Close your private browser window when done.
