# Identity Management — User Accounts

## Overview

This lab uses Active Directory domain accounts to represent individual identities in a small SOC scenario. Centralized identity administration permits accounts and their role-group memberships to be managed from the domain controller.

## Account organization

The group-membership evidence places the recorded user objects in the `SOC-USERS` organizational unit under `soclab.local`.

```text
soclab.local
└── SOC-USERS
```

## Published identity labels

The table below uses neutral labels to avoid republishing lab users' personal or unsuitable display names. These are documentation labels only; they are not a request to rename Active Directory accounts.

| Published label | Intended role | Role group |
|---|---|---|
| `SOC-ADMIN-01` | Administrator | `ADMINS` |
| `SOC-ANALYST-01` | SOC Analyst | `ANALYST` |
| `SOC-SUPPORT-01` | IT Support | `IT-SUPPORT` |
| `SOC-USER-01` | General SOC user | `GG-SOC-USERS` |

## Validation scope

The repository records group membership and domain-client authentication activity. It supports the conclusion that identities were organized and assigned to intended role groups; it does not disclose the underlying account names in this documentation.

## Security considerations

- Use a distinct account for each person or service.
- Assign permissions through role groups rather than directly to users where practical.
- Limit administrative privileges and periodically review group membership.
- Never commit passwords or other credentials.

## Evidence

- [SOC-USERS view](../screenshots/AD-Architecture/active-directory-soc-users.png)
- [ANALYST group membership](../screenshots/Identity-and-RBAC/analyst-members.png)
- [GG-SOC-USERS membership](../screenshots/Identity-and-RBAC/gg-soc-users-members.png)
