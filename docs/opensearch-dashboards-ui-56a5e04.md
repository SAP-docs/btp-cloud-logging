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

