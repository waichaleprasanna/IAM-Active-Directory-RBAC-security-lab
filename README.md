# IAM Active Directory RBAC Security Lab

A hands-on Identity and Access Management (IAM) cybersecurity lab built using Windows Server 2022 and Active Directory Domain Services (AD DS).

This project demonstrates centralized identity management, Role-Based Access Control (RBAC), domain authentication, security policy enforcement, and authentication event monitoring in a controlled lab environment.

## Project Overview

Identity and Access Management is a fundamental component of enterprise cybersecurity. Organizations use IAM to manage digital identities, control access to resources, and enforce security policies.

This lab simulates a small Security Operations Center (SOC) environment using Active Directory to manage domain users, organize security groups, and validate identity-related security controls.

The lab consists of a Windows Server 2022 domain controller and a Windows 11 domain-joined client.

## Objectives

- Deploy and configure an Active Directory domain.
- Establish centralized identity management.
- Create and organize domain user accounts.
- Implement Role-Based Access Control using security groups.
- Join a Windows 11 client to the domain.
- Configure and validate authentication security policies.
- Monitor Windows security events related to authentication.
- Document implementation, testing, and troubleshooting procedures.

## Lab Environment

| Component | Configuration |
|---|---|
| Domain Controller | Windows Server 2022 |
| Client Machine | Windows 11 |
| Directory Service | Active Directory Domain Services |
| Domain | `soclab.local` |
| Access Control | Active Directory Security Groups |
| Policy Management | Group Policy |
| Security Monitoring | Windows Security Event Logs |

## Architecture

The Windows Server 2022 domain controller provides centralized directory and authentication services for the `soclab.local` domain.

The Windows 11 client is joined to the domain and uses Active Directory domain credentials for authentication.

```text
                  IAM SECURITY LAB
                        
              Active Directory Domain
                    soclab.local
                        
             Windows Server 2022
                Domain Controller
                        
           ┌────────────┬────────────┐
           │            │            │
       User Mgmt     Security     Group Policy
                      Groups
           │            │            │
           └────────────┴────────────┘
                        │
                  Domain Auth
                        │
                Windows 11 Client
                        │
               Domain User Login
                        │
                Security Event Logs
```

## Project Implementation

### 1. Active Directory Setup

Installation and configuration of Active Directory Domain Services and creation of the `soclab.local` domain.

Documentation: [Active Directory Setup](setup/active-directory.md)

### 2. Windows Client Integration

Joining a Windows 11 client to the Active Directory domain and validating domain authentication.

Documentation: [Windows Client Setup](setup/windows-client.md)

### 3. Identity Management

Creating and managing domain user accounts and organizing identities within Active Directory.

Documentation: [User Account Management](identity-management/user-accounts.md)

### 4. Role-Based Access Control

Organizing users into security groups according to their assigned roles and responsibilities.

### 5. Security Policies and Monitoring

Configuring authentication security controls and reviewing Windows security events to validate identity-related activities.

## Validation

The lab includes validation activities such as:

- Active Directory domain configuration.
- Windows 11 domain joining.
- Domain user authentication.
- Security group membership verification.
- Role-based access control validation.
- Account-lockout policy testing.
- Windows security event review.

Detailed test results and evidence will be documented as the implementation progresses.

## Repository Structure

```text
IAM-Active-Directory-RABC-security-lab/
│
├── README.md
│
├── architecture/
├── setup/
│   ├── active-directory.md
│   └── windows-client.md
│
├── identity-management/
│   └── user-accounts.md
│
├── access-control/
├── security/
├── testing/
├── troubleshooting/
└── screenshots/
```

## Technologies Used

- Windows Server 2022
- Windows 11
- Active Directory Domain Services
- Group Policy
- Active Directory Users and Computers
- Windows Security Event Logs
- Git and GitHub

## Security Considerations

- Use individual accounts for identity management.
- Assign permissions through security groups where possible.
- Restrict administrative privileges.
- Never commit passwords, credentials, or sensitive configuration data.
- Perform security testing only in an authorized lab environment.

## Learning Outcomes

This project provides practical experience with:

- Enterprise identity management.
- Active Directory administration.
- Role-based access control.
- Domain authentication.
- Security policy configuration.
- Authentication event analysis.
- IAM security testing and documentation.

## Project Status

The lab is being developed and documented incrementally. Additional access-control implementation, security validation, monitoring evidence, and troubleshooting documentation will be added as the project progresses.

---

**Author:** Prasanna Waichale

**Repository:** [IAM Active Directory RBAC Security Lab](https://github.com/waichaleprasanna/IAM-Active-Directory-RABC-security-lab)
