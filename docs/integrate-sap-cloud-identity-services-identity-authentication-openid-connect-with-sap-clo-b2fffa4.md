<!-- loiob2fffa48f5974b0396b3aa54f8bc9507 -->

# Integrate SAP Cloud Identity Services - Identity Authentication OpenID Connect with SAP Cloud Logging

Enable secure, centralized user authentication and role management for logging instances with Identity Authentication OpenID Connect.

> ### Caution:  
> Ensure that you consider [SAP BTP Security Recommendation BTP-CLS-0001](https://help.sap.com/docs/btp/sap-btp-security-recommendations-c8a9bb59fe624f0981efa0eff2497d7d/sap-btp-security-recommendations?seclist-index=BTP-CLS-0001&version=Cloud).

This explains how to integrate with SAP Cloud Identity Services - Identity Authentication OpenID Connect. It results in changes in the Identity Authentication tenant and a corresponding OIDC configuration to be used for creating or updating SAP Cloud Logging instances. Access to the Identity Authentication administration console as an administrator is a prerequisite.

> ### Note:  
> We recommend you integrate with Identity Authentication. You can also integrate with other OIDC providers, but there will be no support or documentation.

> ### Note:  
> You can reuse the resulting OIDC configuration for multiple instances of SAP Cloud Logging.



## Obtain OpenID Connect IdP Information

Obtain OpenID Connect Identity Provider \(IdP\) Information based on the [Identity Authentication guide](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/create-openid-connect-application). Use the console URL to access the tenant’s administration console for the Identity Authentication service. The URL has a `https://<tenantID>.accounts.ondemand.com/admin` pattern.

-   Note down the `openid_connect_url` information as

    ```
    https://<tenantID>.accounts.ondemand.com/.well-known/openid-configuration
    ```




## Create an OpenID Connect application

Create an OpenID Connect application in your Identity Authentication account based on the [Identity Authentication guide](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/create-openid-connect-application). Create OpenID client secrets based on the [Configuration Guide](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/auth-configure-secrets-for-api-authentication)



## Configure the OpenID Connect application

Go to *Applications & Resources*, choose *Applications*, and select your application from the list. Then perform the following steps to configure the OpenID Connect application within Identity Authentication:

1.  [Configure a Self-Defined Attribute](https://help.sap.com/docs/identity-authentication/identity-authentication/user-attributes?version=Cloud) with *Name*: "groups," *Source*: "Identity Directory," and *Value*: "All Groups".
2.  [Configure Default Name ID Format](https://help.sap.com/docs/identity-authentication/identity-authentication/configure-subject-name-identifier-sent-to-application?version=Cloud) to *Email*.
3.  Select *OpenID Connect Configuration* and *Configure Manually*.
    -   This step can only be done after an SAP Cloud Logging instance has been created and has to be repeated for each new service instance.
        -   Set `Redirect URI` to the OpenSearch Dashboards URL plus`/auth/openid/login`.
        -   Set `Single Logout Endpoint`: Set binding to HTTP\_REDIRECT and the URL must be the OpenSearch Dashboards URL without any path.
        -   To store the configuration, choose *Save* .





## Create a Group and Assign Users

-   [Create a group](https://help.sap.com/docs/identity-authentication/identity-authentication/create-new-user-group) that you intend to use for administrative access to SAP Cloud Logging instances and provide the name of this group as the input value for `admin_group` during the OIDC configuration. This group gets administrative access in OpenSearch. It has permission to modify the security module.

    > ### Note:  
    > The login procedure forwards Identity Authentication group names to OpenSearch as backend roles. Backend roles can map to OpenSearch roles that grant permissions to the users assigned to the respective Identity Authentication groups. The configuration parameter `admin_group` is mapped automatically to the `all_access` role.

-   [Add users to the group](https://help.sap.com/docs/identity-authentication/identity-authentication/add-users-to-group) who should have admin access. Users can be added or removed at any time.




## Compose OIDC Configuration Parameters

Compose OIDC configuration parameters to be used for service instance creation or updates:


<table>
<tr>
<th valign="top">

OIDC Configuration Template

</th>
<th valign="top">

Parameterization

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

```
"oidc": {
    "enabled": true,
    "roles_key": "groups",
    "admin_group": "MY_ADMIN_ROLE",
    "subject_key": "mail",
    "openid_connect_url": "https://MY-OPENID-CONNECT-URL/.well-known/openid-configuration",
    "openid_scopes": "openid",
    "openid_client_id": "MY-CLIENT-ID",
    "openid_client_secret": "MY-CLIENT-SECRET"
  }


```



</td>
<td valign="top">

Set IdP information `openid_connect_url` \(for example: `https://myaccount.accounts.ondemand.com/.well-known/openid-configuration`\).

</td>
</tr>
<tr>
<td valign="top">

Set `openid_client_id` and `openid_client_secret` from the Create an OpenID Connect application step.

</td>
</tr>
<tr>
<td valign="top">

Set `admin_group` to the name of the group created in the Create a Group and Assign Users step.

</td>
</tr>
<tr>
<td valign="top">

Optionally, set `openid_scopes` as a space-separated string list if more than one scope is required \(for example: `"openid profile address"`\).

</td>
</tr>
</table>

See [Configuring Applications](https://help.sap.com/docs/identity-authentication/identity-authentication/configuring-applications) in Identity Authentication Service.

