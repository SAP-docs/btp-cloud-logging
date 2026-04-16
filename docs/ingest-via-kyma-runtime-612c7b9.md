<!-- loio612c7b9e0c2644fba43295a7629855bd -->

# Ingest via Kyma Runtime

Kyma's [Telemetry](https://help.sap.com/docs/btp/sap-business-technology-platform/kyma-telemetry-module) module supports shipping observability signals to SAP Cloud Logging instances. You can configure different observability signal types independently of each other.

To integrate Cloud Logging on SAP BTP, Kyma runtime, see [Telemetry Module: Integrate with SAP Cloud Logging](https://help.sap.com/docs/btp/sap-business-technology-platform/integrate-with-sap-cloud-logging).

After successful integration, you can analyze the ingested data in OpenSearch Dashboards \(see [Access and Analyze Observability Data](access-and-analyze-observability-data-dad5b01.md)\) based on the following index patterns:

1.  `logs-json-istio-envoy-kyma`\* for Istio access logs
2.  `logs-json-kyma*` for application logs
3.  [OpenTelemetry related indices](ingest-via-opentelemetry-api-endpoint-fdc78af.md)

