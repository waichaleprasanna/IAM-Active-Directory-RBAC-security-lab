# IAM Active Directory RBAC Security Lab

A hands-on Identity and Access Management (IAM) security lab built with Windows Server 2022, Active Directory Domain Services (AD DS), and a Windows 11 domain client.

The lab demonstrates centralized identity management, role-based group administration, domain authentication, account-lockout policy configuration, and Windows Security event review in the `soclab.local` domain.

## Lab environment

| Component | Configuration |
|---|---|
| Domain controller | Windows Server 2022 |
| Client | Windows 11 |
| Directory service | Active Directory Domain Services |
| Domain | `soclab.local` |
| Access-control model | Active Directory security groups |
| Policy management | Group Policy |
| Monitoring | Windows Security Event Logs |

## Architecture

The Windows Server 2022 domain controller provides directory, DNS, authentication, and policy services for `soclab.local`. The Windows 11 client is domain joined and is used to test identity and access controls.

![Active Directory OU view](screenshots/AD-Architecture/active-directory-domain-ous.png)

## Documentation

| Area | Description |
|---|---|
| [Active Directory setup](setup/active-directory.md) | Domain foundation, DNS role, verified directory organization, and evidence. |
| [Windows client setup](setup/windows-client.md) | Domain-client role and the validation scope recorded for the lab. |
| [User accounts](identity-management/user-accounts.md) | Identity-management approach and redacted documentation labels. |
| [RBAC implementation](access-control/rbac-implementation.md) | Security groups, membership evidence, and resource-access evidence. |
| [Account lockout and monitoring](security/account-lockout.md) | Recorded policy values and observed authentication/lockout evidence. |
| [Test cases](testing/test-cases.md) | Evidence-linked validation status and remaining gaps. |

## Evidence highlights

- The AD Users and Computers view shows the `soclab.local` domain and lab OUs, including `SOC-GROUPS` and `SOC-USERS`.
- Group membership evidence records users assigned to role groups. A resource-access test also records an access-denied result for a protected share.
- The default domain password-policy output records a lockout threshold of five attempts, with a 30-minute lockout duration and observation window.
- Security logs include failed-logon Event ID 4625 and account-lockout Event ID 4740 evidence.

See the [test cases](testing/test-cases.md) for the precise status of each claim. In particular, Event ID 4767 (account unlock) is not recorded in the repository and is not claimed as validated.

## Repository structure

```text
IAM-Active-Directory-RABC-security-lab/
├── README.md
├── setup/
├── identity-management/
├── access-control/
├── security/
├── testing/
└── screenshots/
    ├── AD-Architecture/
    ├── Identity-and-RBAC/
    ├── Resource-Permissions/
    ├── Access-Testing/
    └── Security-Monitoring/
```

## Security notes

- Use individual accounts and assign resource permissions through groups where practical.
- Apply least privilege and periodically review group membership.
- Do not commit passwords, credentials, or sensitive configuration data.
- Perform testing only in an authorized lab environment.

## Project status

The repository documents the Active Directory foundation, role-group organization, resource-access testing, and observed authentication/lockout events. The remaining documented gap is verification of an account-unlock audit event (4767).

---

**Author:** Prasanna Waichale
**Repository:** [IAM Active Directory RBAC Security Lab](https://github.com/waichaleprasanna/IAM-Active-Directory-RABC-security-lab)
