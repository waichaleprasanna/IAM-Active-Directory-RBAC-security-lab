\# IAM Active Directory Lab



A hands-on Identity and Access Management (IAM) lab built using Windows Server 2022 and Active Directory Domain Services (AD DS).



This project demonstrates centralized identity management, role-based access control (RBAC), authentication security policies, and security event validation in a controlled lab environment.



\## Project Overview



Organizations use Identity and Access Management to control who can access systems and resources. This lab explores how Active Directory can be used to manage domain identities, organize users into role-based groups, and validate authentication security controls.



The lab uses a Windows Server 2022 domain controller and a Windows 11 domain-joined client.



\## Objectives



\- Deploy an Active Directory domain.

\- Create and organize domain users and security groups.

\- Join a Windows 11 client to the domain.

\- Implement role-based access control using security groups.

\- Configure and verify account-lockout policies.

\- Review Windows security events related to authentication.

\- Test and document identity security controls.



\## Lab Environment



| Component | Configuration |

|---|---|

| Domain Controller | Windows Server 2022 |

| Client | Windows 11 |

| Directory Service | Active Directory Domain Services |

| Domain | `soclab.local` |

| Access Control | Active Directory security groups |

| Policy Management | Group Policy |

| Security Event Review | Windows Security Event Logs |



\## Architecture



The Windows Server 2022 domain controller provides centralized identity management for the `soclab.local` domain.



The Windows 11 client joins the domain and authenticates domain users through Active Directory.



!\[IAM Lab Architecture](architecture/iam-architecture.png)



\## Project Components



\### Active Directory Setup

Installation and configuration of Active Directory Domain Services and the lab domain.



\### Identity Management

Creation and organization of domain user accounts and security groups.



\### Role-Based Access Control

Assignment of users to role-based security groups and validation of group membership and access.



\### Security Policies and Auditing

Configuration and verification of account-lockout settings, failed authentication attempts, and related Windows security events.



\## Validation



The following activities were tested in the lab:



\- Windows 11 domain join

\- Domain user authentication

\- Security group membership verification

\- Role-based access validation

\- Account-lockout policy verification

\- Account-lockout event review

\- Account unlock and recovery



\## Repository Structure



```text

iam-active-directory-lab/

├── README.md

├── architecture/

├── setup/

├── identity-management/

├── access-control/

├── security/

├── testing/

├── troubleshooting/

└── screenshots/



