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

| Published identity label | Intended role | Assigned group | Membership evidence |
|---|---|---|---|
| `SOC-ADMIN-01` | Administrator | `ADMINS` | Assignment documented; no dedicated member-list capture is present. |
| `SOC-ANALYST-01` | SOC Analyst | `ANALYST` | [Recorded](../screenshots/Identity-and-RBAC/analyst-members.png) |
| `SOC-SUPPORT-01` | IT Support | `IT-SUPPORT` | Assignment documented; no dedicated member-list capture is present. |
| `SOC-USER-01` | General SOC user | `GG-SOC-USERS` | [Recorded](../screenshots/Identity-and-RBAC/gg-soc-users-members.png) |

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

Creating groups and adding members establishes the RBAC structure. Effective enforcement requires resource permissions to be assigned to those groups and then tested. The repository contains successful-open and access-denied screenshots for the protected `\\Soc-dc\admin_files` share; it does not contain a share-ACL capture or an identity-bearing capture for either result.

## Resource-access validation

| Test | Recorded result | What it proves | What is still needed for a complete RBAC proof |
|---|---|---|---|
| Open `\\Soc-dc\admin_files` | Share contents are visible. | The share was reachable and opened successfully. | Capture the signed-in identity and the share/NTFS ACL showing the authorized role group. |
| Open `\\Soc-dc\admin_files` without permission | Windows reports access denied. | An access denial occurred for the protected share. | Capture the attempted identity and its group membership, then show that its group is absent from the resource ACL. |

The current evidence therefore demonstrates both access outcomes, but does not conclusively tie either outcome to a specific group’s resource permission. That distinction is retained deliberately so the documentation does not overstate the RBAC claim.

## Validation scope

- Role groups and membership are recorded in Active Directory.
- A successful open and an access-denied outcome are recorded for `\\Soc-dc\admin_files`.
- The available group security tabs describe permissions on the group objects, not the share ACL; they should not be treated as evidence of file-share authorization.

The evidence does not yet prove that a particular group grants a particular user access to a particular resource. Capture the resource's sharing and NTFS permissions alongside a signed-in user and `whoami /groups` output to complete that chain.

## Evidence

- [SOC-GROUPS view](../screenshots/AD-Architecture/active-directory-soc-groups.png)
- [ANALYST group membership](../screenshots/Identity-and-RBAC/analyst-members.png)
- [GG-SOC-USERS membership](../screenshots/Identity-and-RBAC/gg-soc-users-members.png)
- [GG-SOC-USERS security permissions](../screenshots/Identity-and-RBAC/gg-soc-users-security-permissions.png)
- [ADMINS security permissions](../screenshots/Identity-and-RBAC/admins-group-security-permissions.png)
- [Protected-share opened successfully](../screenshots/Resource-Permissions/admin-files-share.png)
- [Protected-share access denied](../screenshots/Resource-Permissions/admin-files-access-denied-dialog.png)
