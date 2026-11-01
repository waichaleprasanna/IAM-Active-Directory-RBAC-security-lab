\# Active Directory Domain Setup



\## 1. Overview



This document describes the Active Directory Domain Services (AD DS) foundation of the IAM lab.



A Windows Server 2022 virtual machine was configured as the domain controller for the lab domain:



\- \*\*Domain:\*\* `soclab.local`

\- \*\*Server operating system:\*\* Windows Server 2022

\- \*\*Directory service:\*\* Active Directory Domain Services (AD DS)



The domain controller provides centralized identity management and authentication for domain-joined systems.



\## 2. Purpose of the Domain Controller



A domain controller is a server that manages domain authentication and directory information.



In this lab, the domain controller is responsible for:



\- Maintaining Active Directory user, computer, and group objects.

\- Authenticating domain users.

\- Managing security group memberships.

\- Supporting centralized security policy management.

\- Providing directory services to the Windows 11 domain client.

\- Recording security events related to authentication and account activity.



Centralizing these functions allows identity and access controls to be managed from one location instead of configuring every client independently.



\## 3. Domain Configuration



The lab uses the Active Directory domain `soclab.local`.



A dedicated domain was established to create a controlled environment for testing identity management and access-control configurations.



The domain controller was configured to provide Active Directory services to the Windows 11 client.



\### Domain details



| Setting | Value |

|---|---|

| Domain name | `soclab.local` |

| Domain controller OS | Windows Server 2022 |

| Directory service | Active Directory Domain Services |

| Client OS | Windows 11 |



Network addresses and other environment-specific values can be added here if required.



\## 4. Active Directory Domain Services



Active Directory Domain Services provides the directory and authentication functionality used by the lab.



The directory stores information about domain users, computers, and security groups. These objects can be organized and managed through Active Directory administrative tools.



AD DS forms the foundation for the identity-management and role-based access-control components of this project.



\## 5. Organizational Units



Organizational Units (OUs) were used to organize directory objects.



The lab's directory structure separates user accounts and security groups to make administration easier.



OUs can also be used to apply Group Policy settings to specific sets of directory objects.



Document the exact OU structure used in the lab here:



```text

soclab.local

└── \[Insert the actual OU names and hierarchy]

```



Replace the placeholder with the actual structure from Active Directory Users and Computers before publishing.



\## 6. DNS and Domain Communication



Domain Name System (DNS) is essential to Active Directory.



Domain clients use DNS to locate domain controllers and discover domain services. The Windows 11 client must use the lab's domain DNS configuration to locate and communicate with `soclab.local`.



Successful domain joining and domain authentication provide practical evidence that the client can communicate with the domain environment.



\## 7. Validation



The Active Directory foundation was validated through the following activities:



\- Confirmed that the `soclab.local` domain was available.

\- Joined the Windows 11 client to the domain.

\- Authenticated using a domain user account.

\- Verified the user's domain group membership.

\- Confirmed that domain-based identity management was functioning.



\## 8. Result



Active Directory Domain Services was successfully established as the centralized identity-management service for the lab.



This configuration provides the foundation for user and group management, role-based access control, and authentication security testing.



\## 9. Evidence



Add screenshots from the lab that demonstrate the completed configuration.



Suggested evidence:



\- Active Directory domain overview

\- Domain controller configuration

\- Organizational Unit structure

\- Windows 11 domain membership



Place the relevant screenshots in the repository's `screenshots/` directory and link them here when ready.





