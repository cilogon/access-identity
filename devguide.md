---
title: "Developer Guide"
---

This guide provides recommendations for ACCESS staff and resource providers when integrating with ACCESS identity management services.
The goal is to provide a uniform and consistent process for users to sign in across ACCESS web sites.

Apps
----
Please see the [app registration](/register-app) page for details on registering a web application for ACCESS authentication.

SSO
---
ACCESS identity management services provide single sign-on (SSO) for registered web applications.
Once a user has logged in to ACCESS in their web browser, they should not be prompted again for their password or Duo MFA for **18 hours**.

ACCESS uses an `access_ci_sso` cookie as a hint to indicate that a user has logged in to ACCESS.
Additionally, ACCESS uses the absence of the `access_ci_sso` cookie as a hint to indicate that a user has logged out of ACCESS.
The cookie has access permissions for any subdomain under access-ci.org.
ACCESS sites set the cookie upon successful login and clear the cookie on logout.
The cookie has an 18 hour lifetime to match the ACCESS SSO session length.
On logout, ACCESS sites should also initiate a CILogon session logout. See the [Logout](#logout) section below for details.

This allows other ACCESS sites to automatically begin the login process on first page load if the cookie is set,
and the login should be seamless due to SSO,
without requiring the user to click the "Login with ACCESS" button or re-enter their password or Duo MFA.
The cookie does not contain any information except whether there has been a successful login recently.
It is just a hint about whether an attempted automatic login would be able to proceed without user input
and would not contain any credential information.

After the user has logged in, sites should check on subsequent page loads if the cookie has been removed by another site,
indicating that the user has initiated logout on another ACCESS site.
Since we want consistent logout across all ACCESS sites, removing the cookie should trigger a local logout at each ACCESS site.

In summary:
* If the `access_ci_sso` cookie is present and the user isn't logged in to the local site, trigger a login flow.
* If the `access_ci_sso` cookie is absent and the user is logged in to the local site, trigger a logout flow.

Login
------
Please refer to the following brief style guide for styling the "Login with ACCESS" button on your site. Within this guide you'll find the appropriate styling that is cohesive with the main ACCESS site which uses the ACCESS yellow, dark grey, and Archivo Narrow font (see: [Archivo_Narrow-FONT.zip](/Archivo_Narrow-FONT.zip)). Adhering to this styling allows the ACCESS brand to remain cohesive and operate within the best practices of UI/web design and development. In a departure from XSEDE, the ACCESS UI team has decided that providing raster-based buttons isn't within the best practice for how we design and develop UI for sites. Instead, buttons and other UI elements should be included as part of the code, according to the following style guide.

![Login with ACCESS - Style Guide](/ACCESS_Login_Button.jpg)

Additional details are provided in [Adobe XD](https://xd.adobe.com/view/d332fba6-6d51-4436-bacd-c807f991e5f7-8661/).

Logout
------
When a user selects logout on an ACCESS site, the site should:
* Clear any site-specific session.
* Delete the `access_ci_sso` cookie (see above).
* Redirect the user's browser to <https://cilogon.org/logout/?skin=access> to terminate the user's CILogon session.

This will ensure that SSO sessions are terminated consistently across ACCESS sites.

Errors
------
Web applications using ACCESS SSO should be prepared to handle a standard
[OpenID Connect Authentication Error Response](https://openid.net/specs/openid-connect-core-1_0.html#AuthError).
To generate an error response for testing purposes, use a `response_type=error` parameter.
For example: <https://cilogon.org/authorize?client_id=cilogon%3A/client_id/447a035ef16030a50c48dad48d64e645&response_type=error&scope=openid&redirect_uri=https%3A//operations.access-ci.org/openid-connect/accessci>

Links
-----
We recommend the following text/links when incorporating additional ACCESS identity management functionality into your web sites.
* [Forgot ACCESS ID?](https://identity.access-ci.org/username-reminder)
* [Forgot ACCESS Password?](https://identity.access-ci.org/password-reset)
* [Register for a new ACCESS ID](https://identity.access-ci.org/new-user)
* [ACCESS ID and Password FAQ](https://identity.access-ci.org/faq)

Please use the links listed above, and do not link directly to <https://registry.access-ci.org>.
