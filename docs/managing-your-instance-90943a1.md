<!-- loio90943a11646a4de0bc9adf8b02167968 -->

# Managing Your Instance



<a name="loio90943a11646a4de0bc9adf8b02167968__section_dwz_why_t3c"/>

## How to share a Cloud Logging instance?

SAP BTP does not natively support service instance sharing across subaccounts, but there are several ways to share access to a Cloud Logging instance across spaces, subaccounts, or environments.

**Cloud Foundry**

The following approaches are available:

-   **Native Cloud Foundry sharing** \(`cf share-service`\): across spaces within the same org, or across orgs on the same Cloud Foundry API endpoint. Credentials are managed automatically. See [Ingest from Cloud Foundry Runtime](https://help.sap.com/docs/cloud-logging/cloud-logging/ingest-via-cloud-foundry-runtime) for detailed steps.
-   **User-Provided Service \(UPS\)** for Cloud Foundry logs/metrics: works across subaccounts, regions, or environments. Requires manual credential management and rotation. See [Ingest from Cloud Foundry Runtime](https://help.sap.com/docs/cloud-logging/cloud-logging/ingest-via-cloud-foundry-runtime) for detailed steps.
-   **User-Provided Service \(UPS\)** for custom shippers: create a UPS holding the service key credentials and bind your application to it. See [Ingest via OpenTelemetry API Endpoint](https://help.sap.com/docs/cloud-logging/cloud-logging/ingest-via-opentelemetry-api-endpoint) \(section "Using user-provided Services"\) for detailed steps.

For detailed guidance, sample scripts, and best practices on credential rotation, see the [Instance Sharing blog post](https://community.sap.com/t5/technology-blog-posts-by-sap/instance-sharing-sap-cloud-logging/ba-p/14179941).

**Kyma**

Create a secret in the **target** namespace populated with the endpoints and credentials of the service key. See the prerequisites section of [Integrate with Cloud Logging](https://kyma-project.io/external-content/telemetry-manager/docs/user/integration/sap-cloud-logging/README.html#prerequisites) for details.

**BTP instance sharing** \(via BTP CLI or SAP BTP Cockpit\)

Limited to environments within the same subaccount. Works across Cloud Foundry, Kyma, and other environments, with credentials managed automatically. See the [BTP CLI reference](https://help.sap.com/docs/btp/btp-cli-command-reference/btp-share-services-instance).



<a name="loio90943a11646a4de0bc9adf8b02167968__section_tq2_xhy_t3c"/>

## Why doesn't changing the retention period affect existing indexes?

When you update the `retention_period` configuration parameter, the new value applies only to newly created indexes. Existing indexes retain the period that was active when they were created. This is the default OpenSearch behavior — it ensures that policy updates don't affect indexes already under an older policy version, preventing both premature deletion when the period is decreased and delayed deletion when it is increased.

To apply updated retention settings to existing indexes, re-apply the respective lifecycle policy \(ISM policy\) via OpenSearch Dashboards:

1.  Go to *Index Management* \> *Policy managed indexes*.
2.  Note the policy name for the indexes you want to update — it is shown in the *Policy* column \(for example: `retention-policy`\).
3.  Select the indexes you want to update and choose *Change policy*.
4.  Specify the respective indexes in the *Managed indices* field.
5.  Leave *State filters* empty.
6.  Select the policy you noted in step 2.
7.  Select *Keep indices in their current state after the policy takes effect*.
8.  Choose *Change*.

The update runs in the background and may take a while to complete. The UI always shows the latest policy version, so to verify that the correct version is actually applied to an index, use Dev Tools:

```
GET_plugins/_ism/explain/<index>?show_policy=true
```



<a name="loio90943a11646a4de0bc9adf8b02167968__section_jx3_zhy_t3c"/>

## Can the service plan be upgraded or downgraded?

Upgrading or downgrading service plans is not supported. To move to a different plan, use a side-by-side migration:

1.  Create a new Cloud Logging instance with the desired plan.
2.  Configure your senders to send data to both instances simultaneously.
3.  Once the new instance is set up and you are satisfied with the results, switch your observability workflows to the new instance.
4.  Delete the old instance.



<a name="loio90943a11646a4de0bc9adf8b02167968__section_gqn_zhy_t3c"/>

## How to delete a service instance?

All existing bindings and service keys must be deleted before the instance can be deprovisioned. The instance can be deleted via the SAP BTP cockpit, cf CLI, Kyma / BTP Operator, or btp CLI.

> ### Note:  
> It is recommended to use the same mechanism to delete an instance as was used to create it.



<a name="loio90943a11646a4de0bc9adf8b02167968__section_xls_zhy_t3c"/>

## Why does binding an application to Cloud Logging fail?

This can happen if the service instance has not finished provisioning, or if it is unhealthy.

Instance creation can take up to a few minutes. Check the status via the SAP BTP cockpit or your provisioning tool before attempting to bind.

If the instance is fully provisioned but the binding still fails, retry the binding. Ask for support in case it fails frequently.



<a name="loio90943a11646a4de0bc9adf8b02167968__section_x3x_zhy_t3c"/>

## How to monitor the current disk utilization?

The *\[UsageMetrics\] Dashboard* is the recommended way to check current storage utilization and the curation threshold. Open it from the *Dashboards* menu.

For a detailed per-index breakdown, go to *Index Management* \> *Indexes*.

> ### Note:  
> Indexes starting with `.` are system indexes and should not be interfered with.

