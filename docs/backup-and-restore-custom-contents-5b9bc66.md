<!-- loio5b9bc66e65be442489f30931b131d1f6 -->

# Backup and Restore Custom Contents

SAP Cloud Logging service automatically creates a backup of selected instance-related information. Based on this information, instances can be recreated, for example, after an accidental deprovisioning or deletion.



<a name="loio5b9bc66e65be442489f30931b131d1f6__section_wfj_334_xcc"/>

## What is Automatically Backed Up

Only a subset of the configuration is backed up. Take measures if you require more to be backed up.


<table>
<tr>
<th valign="top">

Information

</th>
<th valign="top">

Comment

</th>
</tr>
<tr>
<td valign="top">

`Opensearch settings`

</td>
<td valign="top">

Supported: roles/rolemappings/tenants/groups/security configuration/saved objects/ismpolicy

</td>
</tr>
<tr>
<td valign="top">

`alerts`

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>



<a name="loio5b9bc66e65be442489f30931b131d1f6__section_vtd_t34_xcc"/>

## How to Restore

To restore a Cloud Logging Instance, report the incident \([How to report an incident](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5dd739823b824b539eee47b7860a00be.html)\).

The ticket which requests the restoration must contain the following information:

1.  Support component for this service: `BC-CP-CLS`
2.  The dashboard URL.
3.  Configuration information related to the instance \(the instance name, the subaccount, the retention of the instance, etc.\).
4.  The time when the instance was deprovisioned or deleted.
5.  The status of date to be restored \(no older than 7 days\).
6.  The instance owner information \(cockpit subaccount/team name\).
7.  The reason to restore instead of creating a new instance.

