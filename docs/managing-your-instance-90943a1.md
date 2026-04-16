<!-- loio90943a11646a4de0bc9adf8b02167968 -->

# Managing Your Instance



<a name="loio90943a11646a4de0bc9adf8b02167968__section_dwz_why_t3c"/>

## How to share a Cloud Logging instance?

SAP BTP does not natively support service instance sharing across subaccounts. However, you can share access to a Cloud Logging instance by creating a service key and providing its endpoints and credentials to any sender that needs to ship data to it.

Below you can find examples for Cloud Foundry and Kyma.

For Cloud Foundry \(CF\) applications there are two main approaches:

-   **Native Cloud Foundry sharing**: works across spaces within the same Cloud Foundry org, or across orgs on the same Cloud Foundry API endpoint. Credentials are managed automatically by the platform.

    ```
    cf share-service <SERVICE_INSTANCE> -s <OTHER_SPACE> [-o OTHER-ORG]
    ```

    Then bind your Cloud Foundry application from `<OTHER_SPACE>` as usual. See the [Cloud Foundry documentation](https://docs.cloudfoundry.org/devguide/services/sharing-instances.html) for limitations and security considerations.

-   **User-Provided Service \(UPS\)**: works across any location \(different subaccounts, regions, or environments\). Requires manual credential management and rotation.

    -   For Cloud Foundry log / resource metric ingestion, extract the syslog drain URL from the service key in the **source** subaccount:

        ```
        SYSLOG_DRAIN_URL="$(
        cf service-key <cloud-logging-instance-name> <service-key-name> | \
            tail -n +2 | \
            jq -r '
            .credentials |
            "https-batch://\(.["ingest-username"]):\(.["ingest-password"])@\(.["ingest-endpoint"])/cfsyslog?drain-data=all"
            '
        )"
        ```

        Then, after switching to the **target** subaccount, create a user-provided service:

        ```
        cf create-user-provided-service <ups-name> -l "$SYSLOG_DRAIN_URL" -t "Cloud Logging"
        ```

        The `?drain-data=all` parameter ensures resource metrics are included. Bind your Cloud Foundry application to the user-provided service `<ups-name>`.

    -   For applications using their own shipper \(not the Cloud Foundry syslog integration\), extract the service key credentials in the **source** subaccount:

        ```
        cf service-key <cloud-logging-instance-name> <service-key-name> | \
          tail -n +2 | \
          jq -r '.credentials' \
          > ups.json
        ```

        Then, after switching to the **target** subaccount, create a user-provided service from it:

        ```
        cf create-user-provided-service <ups-name> -p ups.json -t "Cloud Logging"
        ```

        Bind your CF application to the user-provided service `<ups-name>`.



For detailed guidance, sample scripts, and best practices on credential rotation, see the [Instance Sharing blog post](https://community.sap.com/t5/technology-blog-posts-by-sap/instance-sharing-sap-cloud-logging/ba-p/14179941).

For Kyma applications you can create a secret in the **target** namespace \(similar like described in the prerequisites section of the [Integrate with Cloud Logging](https://kyma-project.io/external-content/telemetry-manager/docs/user/integration/sap-cloud-logging/README.html#prerequisites) guide\). This secret can be populated with the endpoints and credentials of the respective Cloud Logging that you want to target.



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

