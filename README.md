
# Role Group Overrides

## Description

**Role Group Overrides** provides a centralized mechanism for managing exception-based group memberships for groups that are otherwise governed and maintained by NIM automation. The application enables administrators to grant temporary or permanent group memberships to specific users without modifying the underlying automated provisioning logic.

Designed to support controlled access exceptions, the application allows authorized users to add, manage, and track membership overrides across managed systems such as Active Directory and Google Workspace, with the flexibility to extend support to additional platforms.

### Key Capabilities

- View all groups that currently contain membership overrides, including the number of users with active overrides.
- Add multiple users to a managed group through a single operation.
- Manage override details, including expiration dates and justification notes.
- Support temporary access assignments through configurable expiration controls.
- Maintain visibility into exception-based access outside of standard role assignments.
- Automatically integrate override memberships into the NIM Role Model through scheduled Role Generation processes.
- Extensible architecture supporting additional group-based systems such as:
  - Adobe Groups
  - Exchange Online Distribution Groups
  - Azure Unified Groups
  - Other supported directory or application platforms

By providing structured management of access exceptions, Role Group Overrides helps organizations maintain governance, improve auditability, and reduce the administrative burden associated with manual group membership management while preserving automated provisioning integrity.


> [!WARNING]
> Groups managed by this app become managed by NIM, thus should only be used with Role Managed Groups.
>
> If Group Overrides are added for non managed groups, they will become managed and have all their members remove except those defined in this app.

## Installation
 1. Import the attached Repository.
 2. Restore only the Lookup table first: RoleGroupOverrides
 3. Update the Internal System to include the new RoleGroupOverrides table.
 4. On the Columns tab of the Internal RoleGroupOverrides table, set the Key to the ID column, and the ExpiresOn datatype to Date.
 5. On the Relations tab, relate the GroupID_Number to the 'groups' Internal table, and the MemberID_Number to the 'users' Internal table.
 6. Restore everything else in the repository.
 7. Grant access to the new app as needed.
