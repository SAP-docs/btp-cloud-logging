<!-- loio5b9bc66e65be442489f30931b131d1f6 -->

# Backup and Restore Custom Contents

SAP Cloud Logging service automatically creates a backup of selected instance-related content (see the supported content list below). You can restore backed-up objects after an accidental deletion.

<a name="loio5b9bc66e65be442489f30931b131d1f6__section_wfj_334_xcc"/>

## What is Automatically Backed Up

> ### Note
>
> Only a subset of all contents is backed up. Take your own measures for other contents. 
>
> Content not mentioned in the list below isn't backed up, for example: alerts and related content, index templates, and so on.

Supported content:

* Saved Objects
  * dashboard
  * visualization
  * index-pattern
  * search
  * config (Advanced Configuration)
* ISM Policies
* Security
  * roles
  * role mappings
  * tenants
  * groups

<a name="loio5b9bc66e65be442489f30931b131d1f6__section_vtd_t34_xcc"/>

## How to Restore

To restore backed up content to a Cloud Logging Instance, report the incident \([How to report an incident](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5dd739823b824b539eee47b7860a00be.html)\).

The ticket which requests the restoration must contain the following information:

1. Support component for this service: `BC-CP-CLS`
2. The dashboard URL.
3. Configuration information related to the instance \(the instance name, the subaccount, the retention of the instance, etc.\).
4. The time when the content was deleted.
5. The status of date to be restored \(no older than 7 days\).
6. The instance owner information \(cockpit subaccount/team name\).
7. The reason to restore instead of re-creating objects.
