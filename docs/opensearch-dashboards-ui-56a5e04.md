<!-- loio56a5e041a18341a5b35d85b360f7d591 -->

# OpenSearch Dashboards UI



<a name="loio56a5e041a18341a5b35d85b360f7d591__section_mk2_ddy_t3c"/>

## Which tenant to use in OpenSearch Dashboards?

We recommend using the **Global** tenant. Cloud Logging uploads its default content — dashboards, index patterns, and visualizations — to the Global tenant only.

Tenants in OpenSearch Dashboards are isolated spaces for saving index patterns, visualizations, dashboards, and other objects. All users have access to two tenants by default: **Global** \(shared between all users\) and **Private** \(exclusive to each user\). The active tenant can be changed at any time in the OpenSearch Dashboards UI.

For more details, see the [OpenSearch multi-tenancy documentation](https://opensearch.org/docs/2.19/security-plugin/access-control/multi-tenancy/).



<a name="loio56a5e041a18341a5b35d85b360f7d591__section_o14_ddy_t3c"/>

## What are `.keyword` fields in OpenSearch?

When browsing your index patterns in OpenSearch Dashboards \(*Dashboards Management* \> *Index Patterns*\), you may notice that string fields appear twice — as `<field>` and `<field>.keyword`. This is by design.

OpenSearch indexes string fields in two ways to support different use cases:

-   type `text`: used for full-text search. The value is tokenized into words, enabling queries like ***find logs containing the word 'error'***.
-   type `keyword`: used for exact matching, sorting, filtering, and aggregations. The value is stored as-is, making it suitable for visualizations and precise filters.

Having both fields available gives you the full range of search and aggregation capabilities without any additional configuration.



<a name="loio56a5e041a18341a5b35d85b360f7d591__section_n21_2dy_t3c"/>

## How to import and export dashboards?

Go to **Dashboards Management → Saved Objects**.

To **export**: search or filter for the dashboards you want, select them, and choose **Export**. Keep the **Include related objects** option enabled to include all associated visualizations and index patterns. The export file will be in NDJSON format.

To **import**: choose **Import**, select your NDJSON file, and choose how to handle any conflicts with existing objects.



<a name="loio56a5e041a18341a5b35d85b360f7d591__section_wp1_htg_cjc"/>

## Why are read-only users missing navigation menu items in OpenSearch Dashboards?

If read-only users can only see the *Discover* and *Dashboards* panels while all other menu items \(for example, Observability, Plugins and Management\) are missing, the `kibana_read_only` backend role is most likely the cause.

The `kibana_read_only` role is a built-in OpenSearch role that hides most of the sidebar navigation. It was designed to limit the UI to only *Discover* and *Dashboards*, but in practice, it is too restrictive for most use cases. It effectively overrides other roles, so even if `readall` or `observability_read_access` are assigned, the navigation remains hidden as long as `kibana_read_only` is part of the role mapping.

To resolve this, remove `kibana_read_only` from the backend role mapping of the affected user or group:

1.  Log in to OpenSearch Dashboards as a user who has permissions to make security changes \(for example, the admin user\).
2.  Navigate to *Security* \> *Roles*.
3.  Select the `kibana_read_only` role.
4.  Navigate to the *Mapped users* tab.
5.  Remove the affected user or group from the mapping.

After removing the role, the missing navigation sidebar elements will be visible again on the next login. Read-only restrictions from other assigned roles will still remain intact.

The `kibana_read_only` role is not required for read-only access. You can refer to this [blog post](https://community.sap.com/t5/technology-blog-posts-by-sap/sap-cloud-logging-service-configuration-of-a-read-only-user/ba-p/13603941) to see an example of how to configure a read-only user.

