---
title: "Privacy"
---

ACCESS InCommon Identity Provider
--------------------------------

The ACCESS InCommon Identity Provider (IdP) at idp.access-ci.org allows ACCESS users to sign in to web sites that are part of the [InCommon Federation](https://incommon.org/federation/) (including ACCESS web sites) using their ACCESS accounts. This capability is especially useful for users who do not have an existing InCommon IdP provided by their home institution.

When signing in to a service that supports InCommon IdPs, first try using your home institution's IdP. If that option isn't available, choose ACCESS from the list of IdPs to sign in with your ACCESS account. Your web browser will be redirected to idp.access-ci.org to complete the sign-in operation. The ACCESS IdP will prompt for Duo authentication. If you are not enrolled with Duo, you will be prompted to set up Duo. As always, you should only enter your ACCESS password on access-ci.org sites.

The ACCESS IdP implements optional single sign-on (SSO), meaning that if you have already authenticated at idp.access-ci.org recently, you will not be prompted again for your password. To disable SSO for idp.access-ci.org, check the "Don't Remember Login" checkbox so that you will be prompted to sign in next time. If you did not check the "Don't Remember Login" checkbox and would like to be prompted to sign in to idp.access-ci.org, you can do so by clearing your browser cookies for idp.access-ci.org.

The ACCESS IdP conforms to the standards set by the [REFEDS Research and Scholarship](https://refeds.org/category/research-and-scholarship) and [REFEDS Security Incident Response Trust Framework for Federated Identity](https://refeds.org/sirtfi) for global interoperability.

The ACCESS IdP releases the following Research & Scholarship (R&S) attributes to all Service Providers (SPs):

* eduPersonPrincipalName (ePPN)
* eduPersonTargetedID (ePTID)
* eduPersonAssurance
* displayName
* givenName
* sn (surName)
* mail

See [InCommon Federation Attribute Overview](https://incommon.org/federation/attributes/) for more information.

CILogon
-------
ACCESS relies on identity management services provided by CILogon. Please see the [CILogon privacy policy](https://www.cilogon.org/privacy) for details.
