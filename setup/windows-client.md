\# Windows 11 Domain Client Setup



\## 1. Overview



A Windows 11 virtual machine was configured as the domain client for the IAM lab.



The client was joined to the Active Directory domain `soclab.local`, allowing domain users to authenticate using centrally managed identities.



\## 2. Purpose of the Client



The Windows 11 client is used to validate the identity and access controls configured on the domain controller.



It provides a practical environment for testing:



\- Domain user authentication

\- Active Directory group membership

\- Role-based access controls

\- Authentication security policies

\- Account-lockout behavior



\## 3. Domain Join



The Windows 11 client was joined to the `soclab.local` domain.



A successful domain join establishes a trust relationship between the client computer and the domain environment. It allows the client to use domain credentials and communicate with Active Directory services.



\### Domain details



| Setting | Value |

|---|---|

| Client operating system | Windows 11 |

| Active Directory domain | `soclab.local` |

| Authentication | Active Directory domain credentials |



\## 4. Domain Authentication



After joining the domain, domain users can sign in to the Windows 11 client using their domain accounts.



The domain controller validates the user's credentials. The user's security group memberships are then available to Windows for access-control decisions.



Domain authentication was tested using the lab's domain user accounts.



\## 5. Validation



The client configuration was validated through the following checks:



\- Confirmed that the Windows 11 machine was joined to `soclab.local`.

\- Signed in using a domain user account.

\- Verified the logged-in domain identity.

\- Inspected the user's group membership.

\- Confirmed that the client could authenticate against the domain.



\## 6. Result



The Windows 11 client was successfully integrated into the Active Directory domain.



It serves as the client endpoint for testing domain authentication, group-based access control, and account security behavior.



\## 7. Evidence



Add screenshots showing:



\- Windows 11 domain membership

\- Successful domain user sign-in

\- Domain identity verification

\- Group membership verification



Store the screenshots in the repository's `screenshots/` directory and link them here when ready.



