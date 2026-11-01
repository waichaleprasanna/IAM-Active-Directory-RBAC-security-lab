\# IAM Lab Test Cases and Validation



\## 1. Overview



This document records the test cases used to validate the Identity and Access Management (IAM) lab.



The tests cover Active Directory domain integration, user authentication, role-based group membership, and authentication security monitoring.



Test results should reflect the behavior observed in the lab. Tests that have not been fully verified are marked as pending.



\## 2. Test Environment



| Component | Configuration |

|---|---|

| Domain | `soclab.local` |

| Domain Controller | Windows Server 2022 |

| Client | Windows 11 |

| Directory Service | Active Directory Domain Services |

| Access Control | Active Directory Security Groups |

| Monitoring | Windows Security Event Logs |



\## 3. Test Cases



\### TC-01: Active Directory Domain Configuration



| Field | Details |

|---|---|

| Objective | Verify that the Active Directory domain is configured |

| Procedure | Inspect the domain configuration on the domain controller |

| Expected Result | The `soclab.local` domain is available |

| Actual Result | Domain configuration established |

| Status | Completed |



\### TC-02: Windows 11 Domain Join



| Field | Details |

|---|---|

| Objective | Verify that the Windows 11 client is joined to the domain |

| Procedure | Inspect the computer's domain membership |

| Expected Result | The client is joined to `soclab.local` |

| Actual Result | Domain join completed |

| Status | Completed |



\### TC-03: Domain User Authentication



| Field | Details |

|---|---|

| Objective | Verify domain user authentication |

| Procedure | Sign in to Windows 11 using a domain user account |

| Expected Result | The domain user can authenticate |

| Actual Result | Domain authentication tested |

| Status | Completed |



\### TC-04: Security Group Membership



| Field | Details |

|---|---|

| Objective | Verify role-based group assignments |

| Procedure | Inspect user membership in Active Directory security groups |

| Expected Result | Users belong to their intended role groups |

| Actual Result | Group assignments configured |

| Status | Completed |



\### TC-05: Failed Authentication Event



| Field | Details |

|---|---|

| Objective | Verify that failed authentication attempts are recorded |

| Procedure | Attempt authentication using an incorrect password and inspect the Security log |

| Expected Result | A relevant failed authentication event is recorded |

| Actual Result | Failed authentication events observed |

| Event ID | 4625 |

| Status | Observed |



\### TC-06: Account Lockout



| Field | Details |

|---|---|

| Objective | Verify account-lockout behavior |

| Procedure | Trigger repeated failed authentication attempts and inspect the account state |

| Expected Result | The account is locked after the configured threshold is reached |

| Actual Result | Requires additional confirmation |

| Event ID | 4740 |

| Status | Pending |



\### TC-07: Account Unlock



| Field | Details |

|---|---|

| Objective | Verify account recovery |

| Procedure | Unlock the test account through Active Directory administrative tools |

| Expected Result | The account can authenticate after being unlocked |

| Actual Result | Requires additional confirmation |

| Event ID | 4767 |

| Status | Pending |



\## 4. Test Summary



| Category | Status |

|---|---|

| Domain configuration | Completed |

| Windows 11 domain join | Completed |

| Domain authentication | Completed |

| Security group assignments | Completed |

| Failed authentication monitoring | Observed |

| Account lockout | Pending |

| Account unlock | Pending |



\## 5. Evidence Collection



Screenshots should be collected for the following:



\- Active Directory domain configuration.

\- Windows 11 domain membership.

\- Successful domain user authentication.

\- Security group membership.

\- Failed authentication events.

\- Account-lockout policy settings.

\- Account-lockout and unlock events, if observed.



Evidence should be stored in the appropriate folders under `screenshots/`.



\## 6. Conclusion



The IAM lab demonstrates centralized identity management using Active Directory.



The completed tests establish the foundation for domain authentication and role-based identity organization.



Authentication event monitoring has also been investigated. Further testing is required to confirm account-lockout and account-recovery behavior.



The test report will be updated as additional validation is completed.



