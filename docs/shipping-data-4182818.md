<!-- loio41828184ff604455b470034516791937 -->

# Shipping Data



<a name="loio41828184ff604455b470034516791937__section_bhg_qkt_t3c"/>

## Why is data not showing up in Cloud Logging?

If only some data is missing:

-   Check if the [Cloud Logging instance is overloaded](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_ukn_p3t_t3c).
-   Check if requests are being rejected for exceeding the [maximum request payload size](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_lms_p3t_t3c).
-   Check if the [maximum number of fields per index](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_cnw_p3t_t3c) is exceeded.

If data is missing entirely or for a specific time period:

-   Check for expired client certificates. If expired, update the binding or service key to obtain new credentials.
-   In case your disk utilization is too high, old data might be deleted by the disk-utilization-based data curation \(as explained within the [Service Plan](https://help.sap.com/docs/cloud-logging/cloud-logging/service-plans) documentation\). See [How to monitor the current disk utilization?](managing-your-instance-90943a1.md#loio90943a11646a4de0bc9adf8b02167968__section_x3x_zhy_t3c).
-   Check that your client is correctly configured to send data to your Cloud Logging instance.
-   Check if you follow the [ingestion guidelines](https://help.sap.com/docs/cloud-logging/cloud-logging/ingest-observability-data) for shipping observability data.

Furthermore, the logs of your shipper may indicate failed requests or error responses that point to the root cause.

For environment-specific guidance, see:

-   [Why is Cloud Foundry data not showing up?](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_zcf_43t_t3c)
-   [Why is Kyma data not showing up?](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_x41_p3t_t3c)
-   [Why is OpenTelemetry data not showing up?](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_rb2_p3t_t3c)
-   [Why is data sent via the JSON API not showing up?](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_hh3_p3t_t3c)



<a name="loio41828184ff604455b470034516791937__section_zcf_43t_t3c"/>

## Why is Cloud Foundry data not showing up?

Start with the [general troubleshooting steps](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_bhg_qkt_t3c).

Additionally, check the following Cloud Foundry-specific points:

-   Check for ingestion errors in the *Ingestion Overview* dashboard \(under **OpenSearch → DashboardsDashboards**\).
-   Check that the [JSON ingestion endpoint is enabled](https://help.sap.com/docs/cloud-logging/cloud-logging/configuration-parameters#configuration-parameters-for-ingest). It is enabled by default but can be disabled via configuration.
-   Verify that your application is properly configured to send signals to Cloud Logging:
    -   Run `cf env <APP_NAME>` and check that `VCAP_SERVICES` contains a syslog drain URL pointing to your Cloud Logging instance's ingest endpoint. If the URL or credentials are missing or incorrect, unbind and rebind your application. A restart is not required. Signals that were not shipped before the rebind cannot be retrieved.

        ```
        cf unbind-service <APP_NAME><SERVICE_INSTANCE>
        cf bind-service <APP_NAME><SERVICE_INSTANCE>
        ```

    -   If resource metrics are missing, use `?drain-data=all` if using a user-provided service. Resource metrics are stored in the OpenTelemetry metrics indexes \(`metrics-otel-v1-*`\).


-   Check for Loggregator overload. Loggregator is the Cloud Foundry subsystem responsible for forwarding app signals to observability backends such as Cloud Logging. This is indicated by:
    -   [messages lost for application logs](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_srq_43t_t3c),
    -   [app instance exceeded log rate limit logs](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_ovv_43t_t3c).




<a name="loio41828184ff604455b470034516791937__section_srq_43t_t3c"/>

## Why are there logs with `messages lost for application` as message content?

This is a Loggregator notification \(see [Why is Cloud Foundry data not showing up?](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_zcf_43t_t3c)\). It indicates that signals are being dropped because Loggregator's buffer is full. This happens when more signals need to be forwarded than the channel can handle. The throughput is limited by the latency between Loggregator and the Cloud Logging ingest endpoint. Once the buffer exceeds 10,000 signals, the entire queue is dropped.

You can search for these notifications in OpenSearch Dashboards **Discover** using DQL: `"messages lost for application"`

To avoid this:

-   Provision the Cloud Logging instance in a region close to the Cloud Foundry landscape hosting the apps.
-   Reduce the signal volume per application instance.
-   Verify that the `syslog_drain_url` in the Cloud Logging entry of your Cloud Foundry environment variables uses the `https-batch` protocol. Older service bindings may not - rebind if needed. For user-provided services, see [Ingest from Cloud Foundry Runtime](https://help.sap.com/docs/cloud-logging/cloud-logging/ingest-via-cloud-foundry-runtime).



<a name="loio41828184ff604455b470034516791937__section_ovv_43t_t3c"/>

## Why are there logs with `app instance exceeded log rate limit` in the message content?

This is a Loggregator notification \(see [Why is Cloud Foundry data not showing up?](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_zcf_43t_t3c)\). It indicates that signals exceeding the rate limit set by the Cloud Foundry environment are being dropped \(see [SAP BTP Cloud Foundry documentation](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-btp-specific-configurations)\).

You can search for these notifications in OpenSearch Dashboards **Discover** using DQL: `"app instance exceeded log rate limit"`

To avoid this:

-   Identify the application generating excessive signals and reduce its output: adjust log levels, remove unnecessary log statements, or set per-app rate limits to avoid "noisy neighbor" problems.



<a name="loio41828184ff604455b470034516791937__section_x41_p3t_t3c"/>

## Why is Kyma data not showing up?

Start with the [general troubleshooting steps](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_bhg_qkt_t3c).

Additionally, check the following Kyma-specific points:

-   Check for ingestion errors in the *Ingestion Overview* dashboard \(under **OpenSearch → DashboardsDashboards**\).

    > ### Note:  
    > It only covers issues for `logs-json-kyma-*` and `logs-json-istio-envoy-kyma-*` indexes.

-   Check the [troubleshooting guide for the Telemetry module](https://kyma-project.io/external-content/telemetry-manager/docs/user/troubleshooting.html).
-   Check the [Kyma Telemetry module sizing](https://help.sap.com/docs/btp/sap-business-technology-platform/kyma-modules-sizing#telemetry).



<a name="loio41828184ff604455b470034516791937__section_rb2_p3t_t3c"/>

## Why is OpenTelemetry data not showing up?

Start with the [general troubleshooting steps](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_bhg_qkt_t3c).

Additionally, check the following OpenTelemetry-specific points:

-   Check that [OpenTelemetry is enabled](https://help.sap.com/docs/cloud-logging/cloud-logging/configuration-parameters#configuration-parameters-for-ingest_otlp) for your service instance.
-   Check that an exporter using the OTLP/gRPC protocol is configured in your OTel instrumentation - OTLP/HTTP is not supported. Make sure it points to the `ingest-otlp-endpoint` from your service binding, not the `ingest-endpoint` or `ingest-mtls-endpoint`.
-   Check that the client certificates from your service binding are correctly passed to your exporter.
-   Keep your OpenTelemetry SDK and Collector versions up to date and check for incompatibilities between them.
-   Check that [retries are configured](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_bjc_q3t_t3c) on your sender - without retries, transient errors will cause data loss.



<a name="loio41828184ff604455b470034516791937__section_hh3_p3t_t3c"/>

## Why is data sent via the JSON API not showing up?

Start with the [general troubleshooting steps](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_bhg_qkt_t3c).

Additionally, check the following JSON API-specific points:

-   Check for ingestion errors in the *Ingestion Overview* dashboard \(under **OpenSearch → DashboardsDashboards**\).
-   Check that the [ingestion endpoint is enabled](https://help.sap.com/docs/cloud-logging/cloud-logging/configuration-parameters#configuration-parameters-for-ingest) for your service instance - it is enabled by default but can be disabled via configuration.
-   Check that your sender is using the `ingest-endpoint` or `ingest-mtls-endpoint` from your service binding.



<a name="loio41828184ff604455b470034516791937__section_ukn_p3t_t3c"/>

## Is the Cloud Logging instance overloaded?

Overload occurs when the ingestion rate exceeds what the instance can handle. Cloud Logging responds with back pressure - returning retryable error codes to signal senders to slow down.

**How to recognize it:**

-   On the sender side: error response codes and failed request entries in your shipper logs.
-   In Cloud Logging: check the *Usage Metrics* dashboard \(under **OpenSearch → DashboardsDashboards**\). If ingest instances are scaled to the maximum, or the cluster state is yellow or red, the instance is likely under pressure.

**What to do:**

-   Short-term overload: configure [retries with exponential backoff](shipping-data-4182818.md#loio41828184ff604455b470034516791937__section_bjc_q3t_t3c) on the sender: requests will eventually succeed once load drops.
-   Long-term overload: retries alone won't help. Consider adjusting the [scaling configuration](https://help.sap.com/docs/cloud-logging/cloud-logging/configuration-parameters), [switching to a bigger service plan](managing-your-instance-90943a1.md#loio90943a11646a4de0bc9adf8b02167968__section_jx3_zhy_t3c), or reducing the data volume on the sender side.



<a name="loio41828184ff604455b470034516791937__section_lms_p3t_t3c"/>

## What is the maximum request payload size?

Cloud Logging rejects requests with a body size exceeding 4 MiB. A size-based rejection returns HTTP error code 413. This limit applies to all request types sent to Cloud Logging. If you hit this limit, split large batches into smaller requests.



<a name="loio41828184ff604455b470034516791937__section_cnw_p3t_t3c"/>

## What is the maximum number of fields per index?

Cloud Logging uses the OpenSearch default of 1,000 fields per index \(`index.mapping.total_fields.limit`\). When this limit is exceeded, documents containing new fields are rejected.

In practice, the usable limit is closer to 500 for most data, because the default mappings create a `.keyword` sub-field for every string field - effectively using two field slots per ingested string field. See [What are .keyword fields in OpenSearch?](opensearch-dashboards-ui-56a5e04.md#loio56a5e041a18341a5b35d85b360f7d591__section_o14_ddy_t3c).

To check the current field count for an index pattern, go to **Dashboards Management → Index Patterns**, select your index pattern, and check the number of listed fields. Alternatively, use Dev Tools to inspect the full mapping:

```
GET<index-name>/_mapping
```



<a name="loio41828184ff604455b470034516791937__section_bjc_q3t_t3c"/>

## What retry settings should the sender use?

Retry settings ensure data is not lost when Cloud Logging is temporarily overloaded. Strike a balance between retrying persistently and not overwhelming the service with more requests than it can handle.

Configure retries with exponential backoff, as increasing delays between attempts reduce pressure on an already overloaded service while still ensuring data eventually gets through.

Examples for common shippers:

-   **Fluent Bit:** [Ingest via JSON API Endpoint example](https://help.sap.com/docs/cloud-logging/cloud-logging/ingest-via-json-api-endpoint) · [Scheduling and Retries](https://docs.fluentbit.io/manual/administration/scheduling-and-retries)
-   **OpenTelemetry Collector:** [Collector Resiliency](https://opentelemetry.io/docs/collector/resiliency/#sending-queue-in-memory-buffering)

For other shippers, consult the shipper's documentation for retry configuration.

