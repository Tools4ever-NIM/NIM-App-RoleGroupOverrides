
# Role Group Overrides
## Description
The Role Group Overrides app is used to add users to AD/Google/etc Groups that are currently managed by NIM.  It includes the following features:

 - List groups that have overrides.  Includes current count of members with overrides in that group.
 - Easily add multiple users in a single operation.
 - Update the Expiration and Note for any membership override.
 - Each group is added to dedicated Roles in the Role Model via a scheduled RoleGeneration task (recommended to run 5 minutes before the regularly scheduled Provisioning task.)
 - App can be easily expanded to support systems other than AD and Google, such as Adobe Groups, EXO Distribution Groups, or even Azure Unified Groups.
	 - Need to add new filters to pull the groups, and the members of those groups.  These filters use Calculated Fields in order to standardize the required fields (Group Name, Group ID, etc), and these filters are then appended to the base AD filters.
	 - Use the existing AD and Google filters as a reference when adding your own system support.

## WARNING
Groups managed by this app become managed by NIM, thus should only be used with Role Managed Groups.

If Group Overrides are added for non managed groups, they will become managed and have all their members remove except those defined in this app.

## Installation

 1. Import and Restore the attached Repository.
 2. Update the Internal System to include the new RoleGroupOverrides table.
 3. On the Columns tab of the Internal-RoleGroupOverrides table, set the Key to the ID column, and the ExpiresOn datatype to Date.
 4. Grant access to the new app as needed.

 

# NIM Docs
>The official NIM documentation can be found at: https://docs.nimsuite.com