# Account Lockout Policy and Authentication Monitoring

## Overview

This document records the account-lockout policy and authentication-monitoring evidence captured in the `soclab.local` lab. Account lockout reduces the risk of repeated password guessing, while Windows Security logs provide evidence of failed authentication and lockout events.

## Recorded policy values

The `Get-ADDefaultDomainPasswordPolicy` output in the repository records the following domain settings.

| Policy setting | Recorded value |
|---|---|
| Account lockout threshold | 5 failed attempts |
| Account lockout duration | 30 minutes |
| Reset account lockout counter (observation window) | 30 minutes |

## Observed event evidence

| Event ID | Meaning | Status supported by repository evidence |
|---|---|---|
| 4625 | Failed logon | Observed |
| 4740 | User account locked out | Observed |
| 4767 | User account unlocked | Not confirmed |

The Event 4740 record was captured on the domain controller and identifies a locked-out lab account. The documentation intentionally does not repeat that account name. A PowerShell unlock command is present in the screenshot set, but no Event 4767 record is shown; command execution alone is not sufficient to claim audit-event validation.

## Testing and interpretation

The evidence supports that failed logons were reviewed, the configured threshold was reached for a test account, and a 4740 event was recorded. Review event details—such as timestamp, account, caller computer, and failure context—when investigating a lockout. Do not generalize this evidence to other accounts or policies without testing them.

## Evidence

- [Default domain password policy](../screenshots/Security-Monitoring/get-ad-default-domain-password-policy.png)
- [Account-lockout policy settings](../screenshots/Security-Monitoring/default-domain-policy-account-lockout-settings.png)
- [Failed-logon events (4625)](../screenshots/Security-Monitoring/event-viewer-failed-logons-4625.png)
- [Filtered lockout event (4740)](../screenshots/Security-Monitoring/event-viewer-4740-filtered.png)
- [Lockout event details](../screenshots/Security-Monitoring/account-lockout-event-details.png)
- [Client lockout confirmation](../screenshots/Access-Testing/account-lockout-confirmation.png)
- [Unlock-command evidence — not an Event 4767 record](../screenshots/Access-Testing/account-unlock-verification.png)
