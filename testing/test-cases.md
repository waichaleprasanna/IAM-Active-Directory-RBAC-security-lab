# IAM Lab Test Cases and Validation

## Test environment

| Component | Configuration |
|---|---|
| Domain | `soclab.local` |
| Domain controller | Windows Server 2022 |
| Client | Windows 11 |
| Directory service | Active Directory Domain Services |
| Access control | Active Directory security groups |
| Monitoring | Windows Security Event Logs |

## Results

| ID | Test | Evidence-backed result | Status | Evidence |
|---|---|---|---|---|
| TC-01 | Active Directory domain configuration | `soclab.local` and lab OUs are visible in AD Users and Computers. | Completed | [Domain/OU view](../screenshots/AD-Architecture/active-directory-domain-ous.png) |
| TC-02 | Windows 11 domain integration | Prior lab documentation records that the client joined `soclab.local`; a dedicated membership screenshot is not present. | Documented, screenshot gap | [Windows client notes](../setup/windows-client.md) |
| TC-03 | Domain-user authentication | Prior lab documentation records a domain-user sign-in; the repository's available evidence is indirect. | Documented, evidence gap | [Windows client notes](../setup/windows-client.md) |
| TC-04 | Security-group membership | Role-group membership is visible in AD evidence. | Completed | [ANALYST membership](../screenshots/Identity-and-RBAC/analyst-members.png) |
| TC-05 | Protected-share denial | A user was denied access to `\\Soc-dc\admin_files`. | Observed | [Access-denied dialog](../screenshots/Resource-Permissions/admin-files-access-denied-dialog.png) |
| TC-06 | Failed authentication logging | Security log includes Event ID 4625. | Observed | [4625 events](../screenshots/Security-Monitoring/event-viewer-failed-logons-4625.png) |
| TC-07 | Account lockout | Policy output records a threshold of 5; the client confirmation and Event ID 4740 show a lockout occurred. | Observed | [4740 event](../screenshots/Security-Monitoring/event-viewer-4740-filtered.png) |
| TC-08 | Account-unlock audit event | No Event ID 4767 evidence is present. | Not confirmed | [Unlock-command screenshot](../screenshots/Access-Testing/account-unlock-verification.png) |

## Interpretation

The evidence supports the configured lockout policy, failed-logon monitoring, an account-lockout event, role-group membership, and a protected-resource denial. It does not yet support a claim that an unlock audit event was recorded, or that all intended authorization paths have been tested.

## Remaining evidence to collect

- A Windows 11 domain-membership view and a domain-user sign-in/identity verification view.
- An Event ID 4767 record, if the lab needs to claim account-unlock auditing.
- Positive access tests for the resources each role is intended to use.
