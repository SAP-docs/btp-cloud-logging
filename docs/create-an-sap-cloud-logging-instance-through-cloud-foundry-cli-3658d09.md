<!-- loio3658d09227dd43c2bcc7df7d774bb925 -->
# Create an SAP Cloud Logging Instance through Cloud Foundry CLI

<a name="loio3658d09227dd43c2bcc7df7d774bb925__section_w5t_wyy_kzb"/>

## Prerequisites

Before creating an SAP Cloud Logging instance, ensure you have:

- Cloud Foundry CLI installed and configured
- Valid SAP BTP credentials
- Appropriate permissions to create service instances
- Access to a Cloud Foundry space

See [Prerequisites](prerequisites-41d8559.md) for detailed requirements.

<a name="loio3658d09227dd43c2bcc7df7d774bb925__section_ngq_1zy_kzb"/>

## Create a Service Instance

Follow these steps to create your SAP Cloud Logging service instance:

### Step 1: Verify Service Availability

First, check that the SAP Cloud Logging service is available in the marketplace:

```bash
cf marketplace
```

Look for `cloud-logging` in the service list. If it's not visible:
- **Check your org/space**: Ensure you're targeting the correct org and space
- **Verify entitlements**: Confirm your subaccount has the necessary service entitlements
- **Contact administrator**: Request access if the service is not entitled

### Step 2: Create the Service Instance

#### Basic Command Structure

```bash
cf create-service cloud-logging <service_plan> <instance_name> [-c <parameters>]
```

**Parameters:**
- `<service_plan>`: Choose from available plans (see [Service Plans](service-plans-a9d2d1b.md))
- `<instance_name>`: Your custom name for the instance
- `<parameters>`: Optional JSON configuration (see [Configuration Parameters](configuration-parameters-1830bca.md))

#### Basic Example

```bash
cf create-service cloud-logging standard my-logging-instance
```

#### Advanced Example with Configuration

```bash
cf create-service cloud-logging standard my-logging-instance -c '{
   "retention_period": 14,
    "backend": {
       "max_data_nodes": 10,
       "api_enabled": false
    },
    "ingest": {
       "max_instances": 10
    }
}'
```

### Step 3: Monitor Provisioning Progress

#### Check Service Status

Monitor the provisioning process:

```bash
cf services
```

Look for your service instance in the output. The `last operation` column shows the current status.

#### Wait for Completion

- **Status "create in progress"**: Wait for provisioning to complete
- **Status "create succeeded"**: Instance is ready for use
- **Status "create failed"**: See troubleshooting section below

## Common Mistakes and Solutions

### ❌ Missing Service Plan

**Error:** `Service plan is required`

**Solution:** Always specify a service plan:
```bash
# Wrong
cf create-service cloud-logging my-instance

# Correct
cf create-service cloud-logging standard my-instance
```

### ❌ Invalid JSON Configuration

**Error:** `Invalid JSON in -c parameter`

**Solution:** Validate your JSON syntax:
```bash
# Wrong (missing quotes)
cf create-service cloud-logging standard my-instance -c '{retention_period: 14}'

# Correct
cf create-service cloud-logging standard my-instance -c '{"retention_period": 14}'
```

### ❌ Insufficient Permissions

**Error:** `Access is denied`

**Solution:** 
- Verify you're assigned the SpaceDeveloper role
- Check org and space permissions
- Contact your BTP administrator

### ❌ Service Already Exists

**Error:** `Service instance already exists`

**Solution:** Choose a different instance name or delete the existing instance:
```bash
cf delete-service existing-instance-name
```

## Troubleshooting

### Provisioning Takes Too Long

**Symptoms:** Service stuck in "create in progress" for more than 15 minutes

**Actions:**
1. Check BTP cockpit for service instance status
2. Verify quota and entitlements
3. Try creating with minimal configuration first
4. Contact SAP support if issue persists

### Configuration Parameter Errors

**Symptoms:** Service creation fails with configuration-related errors

**Actions:**
1. Validate JSON syntax using online JSON validators
2. Check parameter names against [Configuration Parameters](configuration-parameters-1830bca.md)
3. Start with basic configuration and add parameters incrementally
4. Review parameter value ranges and restrictions

### Service Not Available in Marketplace

**Symptoms:** `cloud-logging` not listed in `cf marketplace`

**Actions:**
1. Verify you're in the correct org/space:
   ```bash
   cf target
   ```
2. Check service entitlements in BTP cockpit
3. Switch to entitled org/space:
   ```bash
   cf target -o <org> -s <space>
   ```

### Quota Exceeded

**Symptoms:** Error about quota limits

**Actions:**
1. Check current service usage:
   ```bash
   cf services
   ```
2. Review quota in BTP cockpit
3. Delete unused service instances
4. Request quota increase from administrator

## Next Steps

After successful creation:

1. **Verify instance**: Check that your service appears in `cf services` with status "create succeeded"
2. **Create service key**: Generate credentials for application binding
3. **Configure applications**: Bind the service to your applications
4. **Test connectivity**: Verify logging data ingestion

For detailed configuration options, see [Configuration Parameters](configuration-parameters-1830bca.md).
For different service plans, see [Service Plans](service-plans-a9d2d1b.md).
