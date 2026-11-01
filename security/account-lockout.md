\# Account Lockout Policy and Authentication Monitoring



\## 1. Overview



This document describes the account-lockout security controls and authentication monitoring activities performed in the Active Directory IAM lab.



Account-lockout policies help protect domain accounts against repeated failed authentication attempts. Windows Security Event Logs provide visibility into authentication activity and account-related security events.



\## 2. Objective



The objectives of this implementation are to:



\- Configure account-lockout security policies.

\- Understand the behavior of failed authentication attempts.

\- Monitor authentication-related Windows security events.

\- Validate account-lockout behavior.

\- Understand account recovery and unlocking procedures.



\## 3. Lab Environment



| Component | Configuration |

|---|---|

| Domain | `soclab.local` |

| Domain Controller | Windows Server 2022 |

| Client | Windows 11 |

| Directory Service | Active Directory Domain Services |

| Policy Management | Group Policy |

| Monitoring | Windows Security Event Logs |



\## 4. Account Lockout Policy



An account-lockout policy limits repeated unsuccessful authentication attempts.



When a user exceeds the configured threshold of failed sign-in attempts, the account may be locked for a specified duration.



The policy typically includes:



| Policy Setting | Description |

|---|---|

| Account Lockout Threshold | Number of failed attempts before lockout |

| Account Lockout Duration | Period for which the account remains locked |

| Reset Account Lockout Counter | Time after which the failed-attempt counter resets |



The actual values configured in the lab should be recorded after verifying the policy settings.



\## 5. Authentication Monitoring



Windows Security Event Logs provide information about authentication activity.



The Security log on the domain controller can be used to investigate failed authentication attempts and account-lockout events.



\### Important Windows Security Event IDs



| Event ID | Description |

|---|---|

| 4624 | Successful logon |

| 4625 | Failed logon |

| 4740 | A user account was locked out |

| 4767 | A user account was unlocked |

| 4771 | Kerberos pre-authentication failed |

| 4776 | Credential validation activity |



These events help administrators investigate authentication failures and identify suspicious account activity.



\## 6. Testing Procedure



The following testing procedure was used to investigate account-lockout behavior.



\### Step 1: Trigger Failed Authentication



Attempt authentication using an incorrect password in the controlled lab environment.



\### Step 2: Review Security Events



Inspect the Windows Security Event Log for failed authentication events.



\### Step 3: Verify Account Lockout



Check whether the account reaches the configured lockout threshold and whether a lockout event is recorded.



\### Step 4: Investigate Event Details



Review relevant event information, including:



\- Account name

\- Event timestamp

\- Failure reason

\- Logon type

\- Source workstation or network address, when available



\### Step 5: Account Recovery



After testing, verify whether the account can be unlocked through the appropriate Active Directory administrative procedure.



\## 7. Troubleshooting Notes



During testing, failed authentication events were observed in the Security log.



Some events displayed timestamps that differed from the time of the test. This required checking the event details and timestamp information.



The account-lockout behavior also required additional investigation because the expected lockout did not initially occur.



Potential causes include:



\- The configured lockout threshold was not reached.

\- The policy was not applied to the account.

\- The failed attempts were associated with a different account.

\- The authentication request was processed by a different system.

\- The event log was displaying events from a different time period.



These conditions should be investigated before concluding that the policy is functioning as expected.



\## 8. Validation Status



The validation status should be updated based on the observed results.



| Test | Status |

|---|---|

| Failed authentication event review | Observed |

| Account-lockout threshold verification | Requires confirmation |

| Event ID 4740 verification | Requires confirmation |

| Account unlock verification | Requires confirmation |



Do not mark a test as successful unless the corresponding behavior has been observed and verified.



\## 9. Security Considerations



\- Use appropriate account-lockout thresholds.

\- Monitor repeated authentication failures.

\- Investigate unusual authentication patterns.

\- Avoid excessive lockout durations that could disrupt legitimate users.

\- Protect administrative accounts.

\- Maintain accurate timestamps and event records.

\- Perform testing only in an authorized environment.



\## 10. Result



This lab demonstrates how account-lockout policies and Windows Security Event Logs can support identity security monitoring.



The implementation provides a foundation for investigating failed authentication attempts, validating account security controls, and understanding account recovery procedures.



\## 11. Evidence



Recommended screenshots:



\- Account-lockout policy configuration.

\- Failed authentication event (4625).

\- Account-lockout event (4740), if observed.

\- Account-unlock event (4767), if observed.

\- Relevant event details from Event Viewer.



Store screenshots in the repository's `screenshots/security-monitoring/` directory.



