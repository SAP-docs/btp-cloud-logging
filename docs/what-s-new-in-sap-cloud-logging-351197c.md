<!-- loio351197c822d248758a1945c10fb9ecdb -->

# What's New in SAP Cloud Logging?





**2024 - 2026**


<table>
<tr>
<th valign="top">

Technical Component

</th>
<th valign="top">

Environment

</th>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action

</th>
<th valign="top">

Lifecycle

</th>
<th valign="top">

Type

</th>
<th valign="top">

Line of Business

</th>
<th valign="top">

Modular Business Process

</th>
<th valign="top">

Product

</th>
<th valign="top">

Latest Revision

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma



</td>
<td valign="top">

OIDC URL Validation During Instance Creation

</td>
<td valign="top">

During instance creation with OIDC, the service evaluates OIDC openid\_connect\_url configuration and rejects it if the URL is incorrect. See [OIDC documentation](https://help.sap.com/docs/cloud-logging/cloud-logging/integrate-sap-cloud-identity-services-identity-authentication-openid-connect-with-sap-cloud-logging?version=Cloud).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-04-27

</td>
<td valign="top">

2026-04-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma



</td>
<td valign="top">

Debugging Guide for Ingestion Errors

</td>
<td valign="top">

A guide for debugging ingestion errors is available within the *Ingestion Overview* dashboard \(under *OpenSearch Dashboards* \> *Dashboards*\).​

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-04-27

</td>
<td valign="top">

2026-04-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Kyma



</td>
<td valign="top">

Start Time Column for Istio Logs

</td>
<td valign="top">

The Kyma *Request & Logs* dashboard was extended by a *start\_time* column for the Istio request logs. The search table is now also sorted by this column in descending order \(newest entries first\).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-04-27

</td>
<td valign="top">

2026-04-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma



</td>
<td valign="top">

GenAI Dashboard preview

</td>
<td valign="top">

The new Generative AI / Agent Dashboard is now available in Preview. Built on OpenTelemetry \(gen\_ai\) conventions, this dashboard allows you to seamlessly test and monitor your GenAI applications using Cloud Logging. Find the dashboard as *\[gen\_ai\] Dashboard* under list of dashboards.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

Beta

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-04-27

</td>
<td valign="top">

2026-04-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma



</td>
<td valign="top">

OIDC support

</td>
<td valign="top">

SAP Cloud Logging now supports OpenID Connect \(OIDC\) integration with Identity Authentication, in addition to the existing SAML-based integration. For more information, see [Prerequisites](https://help.sap.com/docs/cloud-logging/cloud-logging/prerequisites).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-04-02

</td>
<td valign="top">

2026-04-02

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma



</td>
<td valign="top">

Standard Ingest component can now be disabled

</td>
<td valign="top">

The Standard Ingest component is now optional \(similar to the Standard Ingest OTel component\). This is helpful for use cases where ingestion is purely Open Telemetry \(OTel\) based . It is **enabled by default** and can be disabled by setting the new [service configuration](https://help.sap.com/docs/cloud-logging/cloud-logging/configuration-parameters#configuration-parameters-for-ingest) parameter `ingest.enabled` to `false`.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-03-05

</td>
<td valign="top">

2026-03-05

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma



</td>
<td valign="top">

Fix binding delays

</td>
<td valign="top">

Fixed bug that caused bindings to occasionally take longer to succeed

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-03-05

</td>
<td valign="top">

2026-03-05

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma



</td>
<td valign="top">

New regions available

</td>
<td valign="top">

SAP Cloud Logging service is now available on region: `cf-us01 and cf-eu22.` For more information, see [Regions for the Kyma Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-for-kyma-environment?version=Cloud) and [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-03-05

</td>
<td valign="top">

2026-03-05

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

OpenTelemetry Trace Span Ingestion Enhancement

</td>
<td valign="top">

Enhanced ingestion rate for OpenTelemetry trace spans, delivering at least 50% higher throughput across all service plans.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-02-02

</td>
<td valign="top">

2026-02-05

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

OpenSearch and OpenSearch Dashboards update to version 2.19.4

</td>
<td valign="top">

The SAP Cloud Logging service has now updated the OpenSearch and OpenSearch Dashboards to version 2.19.4.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-02-02

</td>
<td valign="top">

2026-02-05

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Configuration setting: storeInSessionStorage Disabled

</td>
<td valign="top">

The OpenSearch Dashboards advanced configuration setting \( `state:storeInSessionStorage` \) has been disabled to mitigate the issue with the link sharing feature, for more information, see [https://github.com/opensearch-project/OpenSearch-Dashboards/issues/7677](https://github.com/opensearch-project/OpenSearch-Dashboards/issues/7677). If required, customers can re-enable the setting.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-01-19

</td>
<td valign="top">

2026-01-22

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

cls-rejected-\* Indices Retention Cap

</td>
<td valign="top">

The retention period of `cls-rejected-*` indices is now capped at 7 days.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-01-19

</td>
<td valign="top">

2026-01-22

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Enhanced Ingestion Scale-Out for Load Bursts

</td>
<td valign="top">

The ingestion scale-out behavior is improved for large plans to handle load bursts more effectively.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-01-08

</td>
<td valign="top">

2026-01-08

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Default zstd Compression for OpenSearch Indexes

</td>
<td valign="top">

Zstd compression is now the default for all new OpenSearch indexes, including `logs-json-*` indexes. For more information, see [OpenSearch documentation](https://docs.opensearch.org/2.19/im-plugin/index-codecs/).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2026-01-08

</td>
<td valign="top">

2026-01-08

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Default zstd Compression for OpenSearch Indexes

</td>
<td valign="top">

Zstd compression is now the default for new OpenSearch indexes, except for `logs-json-*` indexes. The adoption of zstd compression for logs-json-\* indexes is planned for upcoming releases. For more information, see [OpenSearch documentation](https://docs.opensearch.org/2.19/im-plugin/index-codecs/).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-12-11

</td>
<td valign="top">

2025-12-11

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Removed `saml.exchange_key` configuration setting

</td>
<td valign="top">

The optional `saml.exchange_key` configuration setting has been removed and is now managed internally. Users can remove this parameter from their configuration files; if left in place, it will be ignored.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-11-27

</td>
<td valign="top">

2025-11-27

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Improved Error Handling for Overloaded Development Plans

</td>
<td valign="top">

The system now returns a 429 response code instead of a 5xx error when the development plan is overloaded. This change clarifies that the issue is due to rate limits or capacity, not server errors.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-11-13

</td>
<td valign="top">

2025-11-13

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Update of underlying OpenSearch to version 2.19 reaches final adoption state

</td>
<td valign="top">

We highly recommend that all customers update their instances now. This gives you full control over when the brief unavailability of OpenSearch Dashboards occurs in your case.

Starting December 4, 2025, we will initiate force-updates to all remaining instances which may hit your instance during the following few days.

For more information, see SAP Note[3617458](https://me.sap.com/notes/3617458).

</td>
<td valign="top">

Required

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-30

</td>
<td valign="top">

2025-12-04

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New regions available

</td>
<td valign="top">

SAP Cloud Logging service is now available on region: cf-ae01. For more information, see [Regions for the Kyma Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-for-kyma-environment?version=Cloud) and [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-30

</td>
<td valign="top">

2025-10-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Expanded Drill-Down for Cloud Foundry Dashboards

</td>
<td valign="top">

The Cloud Foundry dashboards now allow users to view a greater number of organizations and spaces, providing more comprehensive insights into their cloud environments.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-30

</td>
<td valign="top">

2025-10-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Enhanced Cloud Foundry Latency Dashboard

</td>
<td valign="top">

The Cloud Foundry latency dashboard now uses `trace_id` instead of `correlation_id`. This change aligns slicing and dicing with requests and logs.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-30

</td>
<td valign="top">

2025-10-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Enhanced Cloud Foundry errors dashboard

</td>
<td valign="top">

The Cloud Foundry errors dashboard now includes log levels in a case-insensitive manner. For example: logs with levels `error` and ERROR are both listed.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-30

</td>
<td valign="top">

2025-10-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Enhanced Log Shipment Throughput and Reliability in Cloud Foundry

</td>
<td valign="top">

The log shipment from Cloud Foundry now has improved throughput and reliability. This improvement is achieved through binding, where the broker response selects batched sending. Changes will be consumed on new bindings. To consume batched sending with the user-provided service, see [Ingest from Cloud Foundry Runtime](https://help.sap.com/docs/cloud-logging/cloud-logging/ingest-via-cloud-foundry-runtime).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-16

</td>
<td valign="top">

2025-10-16

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Enhanced Cloud Foundry Metrics Dashboard Sorting

</td>
<td valign="top">

The Cloud Foundry container metrics dashboard now features improved sorting, where metrics instances are ordered lexically rather than numerically.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-16

</td>
<td valign="top">

2025-10-16

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Ingest Configuration Supports `min_instances` Parameter

</td>
<td valign="top">

Configuration for ingest now supports the `min_instances` parameter. This parameter lets you specify the minimum number of ingest instances that are always provisioned. For more information, see [Configuration Parameters for ingest](https://help.sap.com/docs/cloud-logging/cloud-logging/configuration-parameters?q=min&version=Cloud#configuration-parameters-for-ingest).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-02

</td>
<td valign="top">

2025-10-02

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Numerical Interpretation of HTTP Status Codes for Range Queries

</td>
<td valign="top">

HTTP status codes are now interpreted as numbers to allow range queries. Searching over the transition period might cause error messages if non-numerical status codes were indexed.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-09-18

</td>
<td valign="top">

2025-09-18

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Fixed traceID link in the OpenTelemetry index patterns for instances using OpenSearch 2.x \("explore" phase\)

</td>
<td valign="top">

The traceID link in the Open Telemetry index patterns for instances using OpenSearch in the **Explore** phase have been fixed.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-09-04

</td>
<td valign="top">

2025-09-04

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

OpenSearch and OpenSearch Dashboards update to version 2.19.3 for instances in "explore" phase

</td>
<td valign="top">

The SAP Cloud Logging service has now updated the OpenSearch and OpenSearch Dashboards to version 2.19.3 for instances in **explore** phase.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-09-04

</td>
<td valign="top">

2025-09-04

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Array based stacktraces in the field `stacktrace` will now be displayed correctly

</td>
<td valign="top">

Array based stacktraces in the field `stacktrace` will now be displayed correctly

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-09-04

</td>
<td valign="top">

2025-09-04

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New regions available

</td>
<td valign="top">

SAP Cloud Logging service is now available on regions: cf-ch20 and cf-eu01. For more information, see [Regions for the Kyma Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-for-kyma-environment?version=Cloud) and [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-08-06

</td>
<td valign="top">

2025-08-06

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

New regions available

</td>
<td valign="top">

SAP Cloud Logging service is now available on regions: cf-jp31, cf-eu31, cf-ca20, cf-ap31. For more information, see [Regions for the Kyma Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-for-kyma-environment?version=Cloud) and [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-06-30

</td>
<td valign="top">

2025-06-30

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Update to: Improvement of the overall stability of Cloud Logging's OpenSearch clusters by proper OpenTelemetry index sizing.

</td>
<td valign="top">

The overall stability of Cloud Logging's OpenSearch clusters will be improved by proper index sizing, especially in high-ingest and huge storage volume scenarios. To achieve this we already switched from daily indexes to the index rollover approach \(see previous announcement from 17. April 2025 for non OpenTelemetry workload indexes.This announcement deals with OpenTelemetry logs and metrics indexes \(*logs-otel-v1-*, *metrics-otel-v1-*\) targeting the release date - **29./30. October 2025**.

With this change OpenTelemetry logs and metrics index names will have a new format. They won't contain the date suffix anymore \(e.g., `metrics-otel-v1-2025.07.14`\), but a six-digit number suffix \(e.g., `metrics-otel-v1-000032`\). Such an index can contain logs from multiple days. Also, there might be several indexes containing data from the same day.

You are affected only if you are using the OpenTelemetry logs/metrics feature and rely on the old index suffix on your **custom** OpenSearch content / queries. In such cases you need to adapt:

-   Change queries to make them independent of the old index date-suffix.
-   If you want to query data from certain days, you can and should do that via a [range query](https://docs.opensearch.org/docs/2.19/query-dsl/term/range/#date-fields) against the index pattern \(e.g. `metrics-otel-v1-*`\) instead of targeting individual indexes.

-   Information about which indexes are mapped to a certain day, or which days are mapped to a certain index can still be obtained from the index creation date / timestamps of contained documents.

    This will further sharpen the retention policy, meaning that the deletion targets indexes created before the last n X 24 hours \(where n is the retention configuration\) instead of deleting the indexes based on day boundaries \(UTC\). This also fixes untimely deletion of indexes for customer located further away from UTC.




</td>
<td valign="top">

Required

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-10-29

</td>
<td valign="top">

2025-10-29

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry

-   Kyma

-   Other



</td>
<td valign="top">

Cloud Logging service now supports ingestion and visualization of SAP BTP, Cloud Foundry Runtime Container metrics.

</td>
<td valign="top">

Receive SAP BTP, Cloud Foundry runtime resource metrics \(CPU, memory, ...\) on **NEW** bindings or **REBINDS**.

To receive the metrics with user-provided services append `?drain-data=all` to the syslog drain URL.

The new metrics can be investigated in "Container Metrics" dashboard under the "Four Golden Signals" in the navigation. The metrics are stored in OpenTelemetry compatible format and can be access via the `metrics-otel-v1-*` index pattern.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2025-07-24

</td>
<td valign="top">

2025-07-24

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Availability of OpenSearch 2.19

</td>
<td valign="top">

Cloud Logging offers a major version upgrade of underlying OpenSearch towards version 2.19. This brings major advancements and new features. The upgrade can be explored immediately, within 3 months a mandatory migration will be rolled out.

For most instances there should be no actions required.

Check SAP Note [3617458 - SAP Cloud Logging: OpenSearch Stack Update Available](https://me.sap.com/notes/3617458) to understand:

-   The phased rollout
-   Cases where your action might be required
-   How to explore the upgrade



</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">



</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2025-07-10

</td>
<td valign="top">

2025-07-10

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Cloud Logging service is available on sa31

</td>
<td valign="top">

New: Cloud Logging service is available on sa31.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2025-03-31

</td>
<td valign="top">

2025-03-31

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Upcoming OpenSearch Stack Update

</td>
<td valign="top">

Heads-Up: Cloud Logging will upgrade its underlying OpenSearch stack from OpenSearch 1.3 to OpenSearch 2.19. The upgrade will be done in a phased approach allowing for an extensive preview/exploration phase before the eventual forced upgrade.

**Action Required**: For most instances, there should be no changes. However, you might be affected if you are using anything of the following:

-   `mapping types` in your custom indices
-   Destination API to manage destinations
-   Wildcard queries against text fields with the option `case_insensitive:false`

For detailed guidance on how to address these cases and the timelines for the phased rollout, see SAP Note [3617458](https://me.sap.com/notes/3617458).

In case you build dashboards on your own: we noticed a few minor UI glitches \(such as text wrapping, sizing, alignment difference\). We will publish guidance on how to adapt the dashboards in early Q3, 2025.

</td>
<td valign="top">

Required

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2025-06-12

</td>
<td valign="top">

2025-06-12

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Support for Monitoring Security Recommendations

</td>
<td valign="top">

Cloud Logging service now supports [Monitoring Security Recommendations with SAP Cloud ALM](https://help.sap.com/docs/btp/sap-btp-security-recommendations-c8a9bb59fe624f0981efa0eff2497d7d/monitor-security-recommendations-with-sap-cloud-alm?seclist-index=BTP-CLS) 

Please also note [SAP BTP Security Recommendations \(for SAP Cloud Logging Service](https://help.sap.com/docs/btp/sap-btp-security-recommendations-c8a9bb59fe624f0981efa0eff2497d7d/sap-btp-security-recommendations?seclist-index=BTP-CLS)\)

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2025-05-15

</td>
<td valign="top">

2025-05-15

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Loading of Existing Configuration during Instance Update

</td>
<td valign="top">

Cloud Logging enables loading of existing configuration during instance update via cockpit.

Please note: if the last update performed only includes partial parameters, the loading configurations will only bring the last updated partial parameters.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Business Technology Platform

</td>
<td valign="top">

2025-05-15

</td>
<td valign="top">

2025-05-15

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Cloud Logging service is available on US11

</td>
<td valign="top">

The Cloud Logging service is now available on US11

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

Business Technology Platform

</td>
<td valign="top">

2025-02-26

</td>
<td valign="top">

2025-03-06

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

OpenSearch and OpenSearch Dashboards is updated to 1.3.20

</td>
<td valign="top">

We have updated the OpenSearch and OpenSearch Dashboards to 1.3.20

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2501b

</td>
<td valign="top">

2025-02-20

</td>
<td valign="top">

2025-03-06

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Update: "CF Requests and Logs" dashboard shows trace\_id and span\_id columns

</td>
<td valign="top">

We have updated the CF Requests and Logs dashboard to show trace\_id and span\_id columns.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2501a

</td>
<td valign="top">

2025-02-06

</td>
<td valign="top">

2025-03-06

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Update to: Improvement of the overall stability of Cloud Logging's OpenSearch clusters by proper index sizing.

</td>
<td valign="top">

Rollout of Index sizing - Improvement of the overall stability of Cloud Logging's OpenSearch clusters by proper index sizing.

The overall stability of Cloud Logging's OpenSearch clusters will be improved by proper index sizing, especially in high-ingest and huge storage volume scenarios. To achieve this, we will switch from daily indexes to the index rollover approach targeting the updated release date - **17. April 2025**.

With this change, the index names will have a new format. They won't contain the date suffix anymore \(e.g., `logs-json-2024.11.19`\), but a six-digit number \(e.g., `logs-json-000032`\). Such an index can contain logs from multiple days. Also, there might be several indexes containing data from the same day.

You are affected only if you run queries against the old index suffix. In such cases you need to adapt:

-   Change queries to make them independent of the old index date-suffix.

-   If you want to query data from certain days, you can and should do that via a [range query](https://opensearch.org/docs/1.3/query-dsl/term/range/#date-fields) against the index pattern instead of targeting individual indexes.

-   Information about which indexes are mapped to a certain day, or which days are mapped to a certain index can still be obtained from the index creation date / timestamps of contained documents.

This will further sharpen the retention policy, meaning that the deletion targets indexes created before the last n X 24 hours \(where n is the retention configuration\) instead of deleting the indexes based on day boundaries \(UTC\). This also fixes untimely deletion of indexes for customer located further away from UTC.

</td>
<td valign="top">

Required

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2503b

</td>
<td valign="top">

2025-02-10

</td>
<td valign="top">

2025-04-17

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Improvement of the overall stability of Cloud Logging's OpenSearch clusters by proper index sizing.

</td>
<td valign="top">

The overall stability of Cloud Logging's OpenSearch clusters will be improved by proper index sizing, especially in high-ingest and huge storage volume scenarios. To achieve this we will switch from daily indexes to the index rollover approach targeting the 2501a release \(RTC 06.02.25\)

With this change, the index names will have a new format. They won't contain the date suffix anymore \(e.g., `logs-json-2024.11.19`\), but a six-digit number \(e.g. `logs-json-000032`\). Such an index can contain logs from multiple days. Also, there might be several indexes containing data from the same day.

This should not affect most use cases, but if there is strict a dependency on the date suffix in the index name format, this needs to be adapted.

This will further sharpen the retention policy, meaning that the deletion targets indexes created before the last n X 24 hours \(where n is the retention configuration\) instead of deleting the indexes based on day boundaries \(UTC\). This also fixes untimely deletion of indexes for customer located further away from UTC.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2412a

</td>
<td valign="top">

2024-12-06

</td>
<td valign="top">

2024-12-12

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New "Service" Dashboard

</td>
<td valign="top">

A new "Service" dashboard offers detailed information about the usage of the service using its dedicated index.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2412a

</td>
<td valign="top">

2024-12-06

</td>
<td valign="top">

2024-12-12

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Cloud Logging service is now available in IL30

</td>
<td valign="top">

The Cloud Logging service is now available in IL30

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2411b

</td>
<td valign="top">

2024-11-28

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Update OpenSearch and OpenSearch Dashboards to 1.3.19

</td>
<td valign="top">

We have updated the OpenSearch and OpenSearch Dashboards to 1.3.19

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2411b

</td>
<td valign="top">

2024-11-28

</td>
<td valign="top">

2024-11-28

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Dev Plan update

</td>
<td valign="top">

We have enabled storing audit logs for dev plan instances

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2407b

</td>
<td valign="top">

2024-08-08

</td>
<td valign="top">

2024-08-08

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New Updates

</td>
<td valign="top">

We have improved Kyma and Cloud Foundry dashboards by fixing the error visualization in the 4 Golden Signal to show the correct values when filtering.

We have improved ingestion stability by fixing sporadic 502 responses from the ingest endpoint.

We've removed never-supported email destinations from the alerting plugin dropdown.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

2407a

</td>
<td valign="top">

2024-07-25

</td>
<td valign="top">

2024-07-25

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Update OpenSearch

</td>
<td valign="top">

Updated OpenSearch and OpenSearch Dashboards to 1.3.16.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-06-14

</td>
<td valign="top">

2024-06-14

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Update OpenSearch

</td>
<td valign="top">

OpenSearch and OpenSearch Dashboards have been updated to 1.3.15.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-04-18

</td>
<td valign="top">

2024-04-18

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

OpenTelemetry updates

</td>
<td valign="top">

Cloud Logging now provides a dashboard for exploring OpenTelemetry metrics.

It also provides an OpenTelemetry JVM metrics dashboard.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Announcement

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-03-28

</td>
<td valign="top">

2024-03-28

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Updates

</td>
<td valign="top">

Improve index template and index pattern for metric-otel-v1-\* indices.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-02-29

</td>
<td valign="top">

2024-02-29

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Time precision change

</td>
<td valign="top">

Change the time precision for OpenTelemetry documents to date\_nanos to comply with the standard

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-02-15

</td>
<td valign="top">

2024-02-15

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

Several changes to make Cloud Logging more efficient

</td>
<td valign="top">

Improve OpenTelemetry ingest stability for standard and dev plan. Improve OTEL trace ingest performance for large plan by at least 25%

Change build-code plan from standard to dev

Update OpenSearch and OpenSearch Dashboards to 1.3.14

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-02-01

</td>
<td valign="top">

2024-02-01

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

OpenSearch has been updated

</td>
<td valign="top">

We've updated OpenSearch and OpenSearch Dashboards to version 1.3.14.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

Changed

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

 

</td>
<td valign="top">

2024-01-31

</td>
<td valign="top">

2024-01-31

</td>
</tr>
<tr>
<td valign="top">

Cloud Logging

</td>
<td valign="top">

-   Cloud Foundry



</td>
<td valign="top">

New service

</td>
<td valign="top">

SAP Cloud Logging service is an instance-based observability service that builds upon OpenSearch to store, visualize, and analyze application logs, metrics, and traces from SAP BTP Cloud Foundry, Kyma, Kubernetes and other runtime environments. For Cloud Foundry and Kyma, it offers an easy integration by providing predefined contents to investigate load, latency, and error rates of the observed applications based on their requests and correlate them with additional data.

</td>
<td valign="top">

Info only

</td>
<td valign="top">

General Availability

</td>
<td valign="top">

New

</td>
<td valign="top">

Technology

</td>
<td valign="top">

Not applicable

</td>
<td valign="top">

SAP Cloud Logging

</td>
<td valign="top">

2023-12-04

</td>
<td valign="top">

2023-12-04

</td>
</tr>
</table>

