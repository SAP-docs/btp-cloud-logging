<!-- loio834217698bdb47609642ab4001734251 -->

# What Is SAP Cloud Logging?



SAP Cloud Logging service is an instance-based observability service that builds upon OpenSearch to store, visualize, and analyze application logs, metrics, and traces from SAP BTP Cloud Foundry, Kyma, Kubernetes and other runtime environments. For Cloud Foundry and Kyma, it offers an easy integration by providing predefined contents to investigate load, latency, and error rates of the observed applications based on their requests and correlate them with additional data.



## Key Benefits

-   It is natively integrated with SAP BTP, offering seamless observability across Cloud Foundry, Kyma, and Kubernetes runtimes without additional infrastructure.
-   It supports the OpenTelemetry standard for data ingestion, allowing you to ship observability data from modern application stacks with a simple configuration.
-   It can be instantiated directly from the SAP BTP Service Marketplace using the cockpit, Cloud Foundry CLI, btp CLI, or SAP BTP Service Operator, fitting into existing SAP BTP workflows without requiring separate tooling.
-   It supports sharing a single service instance across multiple Cloud Foundry spaces and organizations, reducing overhead when consolidating observability data from multiple applications.



## Features


<dl>
<dt><b>

Store observability data 

</b></dt>
<dd>

Store observability data from SAP BTP workloads. Ingest logs, metrics, and traces via OpenTelemetry format API. Ingest observability data via JSON format API. Ingest application logs and request logs emitted by Cloud Foundry.



</dd><dt><b>

Configure retention 

</b></dt>
<dd>

Persist the ingested observability data for a configurable retention period. Note: This is overruled by size-based curation when the disk runs full.



</dd><dt><b>

View, search, and analyze data 

</b></dt>
<dd>

View, search, filter, and analyze observability data in a web-based user interface using predefined dashboards.



</dd><dt><b>

Create custom dashboards 

</b></dt>
<dd>

Build and persist custom dashboards to analyze your observability data tailored to your specific requirements.



</dd><dt><b>

Configure notifications 

</b></dt>
<dd>

Configure customized notifications derived from the observability data of your applications.



</dd><dt><b>

Manage access 

</b></dt>
<dd>

Enable management of users and group-based access using SAP Identity Authentication Service.



</dd>
</dl>

