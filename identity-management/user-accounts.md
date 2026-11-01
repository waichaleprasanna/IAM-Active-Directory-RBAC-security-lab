\# Identity Management — User Accounts



\## 1. Overview



This document describes how domain user identities were created and managed in the IAM lab using Active Directory.



User accounts represent individual identities that can authenticate to domain-joined systems. Centralized account management allows administrators to manage identities and access from the domain controller.



\## 2. Purpose



The objective of user management in this lab is to demonstrate:



\- Centralized creation and management of domain accounts.

\- Organization of users within Active Directory.

\- Assignment of users to security groups.

\- Domain authentication from the Windows 11 client.

\- Verification of user identity and group membership.



\## 3. Domain User Accounts



The lab contains domain user accounts representing different roles within a small SOC environment.



The accounts are managed in Active Directory under the `soclab.local` domain.



| User account | Intended role |

|---|---|

| `AMARLODU` | Administrator |

| `REVANTHNIGGA` | Analyst |

| `PRATEEKJHATOO` | IT Support |

| `GANDUAKSHAY` | General SOC User |



These accounts are used to validate role-based group assignment and domain authentication.



\## 4. Account Organization



User accounts are organized using Active Directory Organizational Units (OUs).



This provides a logical structure for identity administration and supports the application of policies to selected groups of directory objects.



Document the actual OU containing these users here:



`\[Insert the actual user OU name]`



\## 5. Authentication



The domain user accounts can authenticate to the Windows 11 client using domain credentials.



The domain controller validates the credentials, and Windows uses the user's identity and group membership when evaluating access to domain resources.



\## 6. Validation



User account management was validated by:



\- Confirming that the domain user accounts existed in Active Directory.

\- Signing in to the Windows 11 client with domain credentials.

\- Verifying the logged-in domain identity.

\- Inspecting group membership.

\- Confirming that the accounts were associated with their intended roles.



\## 7. Security Considerations



\- Each user should have an individual account.

\- Permissions should be assigned through role-based groups where possible.

\- Administrative privileges should be limited to accounts that require them.

\- Passwords and credentials should never be committed to the GitHub repository.

\- User accounts should be disabled or removed when they are no longer required.



\## 8. Result



The lab demonstrates centralized domain user management through Active Directory. These identities provide the basis for role-based access control and authentication security testing.



\## 9. Evidence



Add screenshots demonstrating:



\- Domain users in Active Directory Users and Computers.

\- User account properties.

\- Successful domain authentication.

\- Group membership verification.



Place the screenshots in the repository's `screenshots/` directory and link them here when ready.



