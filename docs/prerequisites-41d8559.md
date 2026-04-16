<!-- loio41d8559375b84adda2596d943404d93a -->

# Prerequisites

To create instances of SAP Cloud Logging, you must configure entitlements for SAP Cloud Logging, and integrate SAP Cloud Identity Services - Identity Authentication SAML 2.0 with SAP Cloud Logging.



<a name="loio41d8559375b84adda2596d943404d93a__section_u5p_fjy_kzb"/>

## Configure Entitlements for SAP Cloud Logging

To create a service instance of SAP Cloud Logging, you need:

-   A Global Account, see [Getting a Global Account](https://help.sap.com/docs/btp/sap-business-technology-platform/getting-global-account?version=Cloud).
-   A Subaccount, see [Getting a Subaccount](https://help.sap.com/docs/btp/sap-business-technology-platform/create-subaccount?version=Cloud).
-   A service Entitlement for SAP Cloud Logging, see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/docs/btp/sap-business-technology-platform/configure-entitlements-and-quotas-for-subaccounts?version=Cloud).

Once you have these three prerequisites, the service is available in the Service Marketplace.



## Set Up an Identity Provider for Single Sign-On

To enable users to access SAP Cloud Logging securely, you must configure an Identity Provider \(IdP\) for Single Sign-On \(SSO\). This allows centralized user authentication and authorization through your enterprise identity management system.

We recommend using SAP Cloud Identity Services - Identity Authentication as your IdP. Choose one of the following authentication protocols to integrate with your SAP Cloud Logging instances:

-   [Integrate SAP Cloud Identity Services - Identity Authentication SAML 2.0 with SAP Cloud Logging](integrate-sap-cloud-identity-services-identity-authentication-saml-2-0-with-sap-cloud-log-d7f0258.md) — Configure SAML 2.0 authentication to establish a corresponding SAML configuration for your SAP Cloud Logging instances.
-   [Integrate SAP Cloud Identity Services - Identity Authentication OpenID Connect with SAP Cloud Logging](integrate-sap-cloud-identity-services-identity-authentication-openid-connect-with-sap-clo-b2fffa4.md) — Configure OpenID Connect authentication to establish a corresponding OIDC configuration for your SAP Cloud Logging instances.

