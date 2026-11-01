# Role-Based Access Control (RBAC) Implementation

## Overview

This lab uses Active Directory security groups to organize identities by intended SOC role. This demonstrates role-based identity administration: group membership is managed centrally and can then be used when assigning permissions to resources.

## Security-group structure

| Security group | Intended role |
|---|---|
| `ADMINS` | Administrative operations |
| `ANALYST` | SOC analysis activities |
| `IT-SUPPORT` | IT support operations |
| `GG-SOC-USERS` | General SOC user access |

The evidence shows these groups organized in the `SOC-GROUPS` OU. The user-to-role mapping is documented with neutral labels in [User Accounts](../identity-management/user-accounts.md); those labels do not rename the real AD accounts.

## Access-control flow

```text
Domain user
    ↓
Active Directory identity
    ↓
Role-based security group
    ↓
Permissions assigned to the group
    ↓
Access decision for a resource
```

Creating groups and adding members establishes the RBAC structure. Effective enforcement requires resource permissions to be assigned to those groups and then tested; the repository includes one protected-share access-denied result as evidence of such a test.

## Validation scope

- Role groups and membership are recorded in Active Directory.
- The repository records group security-permission views.
- A user was denied access to the protected `\\Soc-dc\admin_files` share.

The evidence supports an access-denied outcome for that share. It does not, by itself, prove every intended role can access every authorized resource, so broader authorization testing remains outside the documented scope.

## Evidence

- [SOC-GROUPS view](../screenshots/AD-Architecture/active-directory-soc-groups.png)
- [ANALYST group membership](../screenshots/Identity-and-RBAC/analyst-members.png)
- [GG-SOC-USERS membership](../screenshots/Identity-and-RBAC/gg-soc-users-members.png)
- [GG-SOC-USERS security permissions](../screenshots/Identity-and-RBAC/gg-soc-users-security-permissions.png)
- [ADMINS security permissions](../screenshots/Identity-and-RBAC/admins-group-security-permissions.png)
- [Protected-share access denied](../screenshots/Resource-Permissions/admin-files-access-denied-dialog.png)
