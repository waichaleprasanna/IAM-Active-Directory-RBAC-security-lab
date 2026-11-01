# Windows 11 Domain Client Setup

## Overview

A Windows 11 virtual machine is the domain client for the `soclab.local` IAM lab. It is used to exercise domain authentication, group-based access decisions, and account-lockout behavior against the Windows Server 2022 domain controller.

| Setting | Value |
|---|---|
| Client operating system | Windows 11 |
| Active Directory domain | `soclab.local` |
| Authentication | Active Directory domain credentials |

## Domain-client role

Joining a client to the domain establishes a trust relationship that permits domain credentials to be evaluated by the domain controller. The client must be able to resolve the domain through the lab DNS configuration before it can locate domain services.

## Recorded validation

The lab documentation records that the Windows 11 client was joined to `soclab.local`, a domain account was used to authenticate, and group membership was inspected. The repository does not currently contain a dedicated domain-membership screenshot, so this document does not add a screenshot claim beyond the evidence linked in the identity, RBAC, and testing documents.

## Result

The Windows 11 client provides the endpoint used for the lab's domain authentication, role-group, resource-access, and account-lockout tests.
