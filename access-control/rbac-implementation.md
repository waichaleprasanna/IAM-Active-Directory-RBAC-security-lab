\# Role-Based Access Control (RBAC) Implementation



\## 1. Overview



This document describes the implementation of Role-Based Access Control (RBAC) in the Active Directory IAM lab.



RBAC is an access-control approach in which permissions are assigned according to organizational roles rather than directly to individual users.



In this lab, Active Directory security groups are used to represent different roles within a simulated Security Operations Center (SOC) environment.



\## 2. Objective



The objective of this implementation is to:



\- Organize users according to their job responsibilities.

\- Use security groups for centralized access management.

\- Reduce the need to assign permissions individually.

\- Demonstrate role-based identity administration.

\- Validate group membership and domain identity.



\## 3. Lab Environment



| Component | Configuration |

|---|---|

| Domain | `soclab.local` |

| Directory Service | Active Directory Domain Services |

| Domain Controller | Windows Server 2022 |

| Client | Windows 11 |

| Access Control Model | Role-Based Access Control |

| Group Type | Active Directory Security Groups |



\## 4. Security Group Structure



The lab uses Active Directory security groups to represent the different roles in the SOC environment.



| Security Group | Intended Role |

|---|---|

| `ADMINS` | Administrative operations |

| `ANALYST` | SOC analysis activities |

| `IT-SUPPORT` | IT support operations |

| `GG-SOC-USERS` | General SOC user access |



These groups provide a centralized method for organizing user identities and supporting access-control administration.



\## 5. User-to-Role Assignment



The following user accounts were assigned to their corresponding role groups.



| User Account | Assigned Group | Role |

|---|---|---|

| `AMAR MC` | `ADMINS` | Administrator |

| `REVANTH NIGGA` | `ANALYST` | SOC Analyst |

| `PRATEEK JHATOO` | `IT-SUPPORT` | IT Support |

| `GANDU AKSHAY` | `GG-SOC-USERS` | General SOC User |



The assignments were configured in Active Directory and are used to demonstrate role-based identity organization.



\## 6. Implementation Procedure



The RBAC structure was implemented using Active Directory Users and Computers.



\### Step 1: Create Security Groups



Security groups were created in Active Directory to represent the roles required for the lab.



\### Step 2: Organize Groups



The security groups were organized within the `SOC-GROUPS` Organizational Unit.



\### Step 3: Assign Users



Each domain user was added to the security group corresponding to their intended role.



\### Step 4: Verify Membership



Group membership was inspected in Active Directory to confirm that users were assigned to their intended groups.



\## 7. How RBAC Works



The implementation follows this access-control flow:



```text

Domain User

&#x20;   |

&#x20;   v

Active Directory Identity

&#x20;   |

&#x20;   v

Role-Based Security Group

&#x20;   |

&#x20;   v

Group Membership Evaluation

&#x20;   |

&#x20;   v

Access to Assigned Resources

```



When a domain user authenticates, Windows uses the user's security identity and group memberships when evaluating access to resources.



Permissions can be assigned to security groups rather than being individually configured for each user.



\## 8. Validation



The RBAC implementation was validated by:



\- Confirming that the security groups existed in Active Directory.

\- Confirming that the groups were organized in the `SOC-GROUPS` OU.

\- Verifying the user-to-group assignments.

\- Inspecting domain user group membership.

\- Confirming domain authentication from the Windows 11 client.



Resource-level access testing should be documented separately when specific permissions have been configured and tested.



\## 9. Security Considerations



\- Follow the principle of least privilege.

\- Avoid granting administrative permissions to ordinary user accounts.

\- Assign permissions through security groups where practical.

\- Review group membership periodically.

\- Remove users from groups when their responsibilities change.

\- Avoid using privileged groups for routine activities.

\- Maintain evidence of access-control configuration and validation.



\## 10. Result



The lab demonstrates the organization of domain identities using Active Directory security groups.



The implementation establishes a role-based structure for centralized identity administration and provides a foundation for testing access-control policies in a simulated SOC environment.



\## 11. Evidence



Recommended screenshots:



\- Security groups in Active Directory.

\- `SOC-GROUPS` Organizational Unit.

\- Group membership properties.

\- Domain user group membership verification.



Store relevant screenshots in the repository's `screenshots/access-control/` directory.



