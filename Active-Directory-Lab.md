# Active Directory Lab – User & Group Management

## Objective
Practice basic Active Directory administration by creating users, groups,
and managing permissions in a Windows Server lab environment.

## Lab Environment
- Windows Server (Domain Controller)
- Windows 10 Client (joined to domain)
- Active Directory Domain Services (AD DS)

## Tasks Performed

### 1. Domain Setup
- Installed Active Directory Domain Services
- Promoted server to Domain Controller
- Created a new domain (lab environment)

### 2. User Management
- Created multiple domain user accounts
- Set passwords and enforced password policies
- Enabled and disabled user accounts for testing

### 3. Group Management
- Created security groups
- Added users to appropriate groups
- Tested group-based access control

### 4. Organizational Units (OUs)
- Created Organizational Units
- Moved users and groups into OUs
- Applied basic organization structure

### 5. Login & Access Testing
- Joined a Windows client machine to the domain
- Logged in using domain user credentials
- Verified group membership and access

## Tools Used
- Active Directory Users and Computers (ADUC)
- Windows Server
- Windows 10
- Virtual Machine environment

## Security Notes
- Lab performed in an isolated, non-production environment
- No real user data or credentials were used

## Skills Demonstrated
- Active Directory fundamentals
- Identity and access management (IAM)
- User and group administration
- Basic troubleshooting
  

## Installing Active Directory in Windows Server 


### Active Directory Users & Groups
Step 1: Go to Server manager and click on Add roles and Features.
![Server Manager](/images/test1.png)

Step 2: Select the Role based Installation and Select “Next”.
![Server Manager](/images/test2.png)

Step 3: Select the Server from Server Pool.
![Server Manager](/images/test3.png)

Step 4: Select the Active Directory Domain Services feature.
![Server Manager](/images/test4.png)

Then check Active Directory Domain Services in Server Roles, and click Add Features by default in the pop-up window to install active Directory Domain Services.
![Server Manager](/images/test5.png)

Step 5: Confirm page > Click on “Install”.
![Server Manager](/images/test6.png)

Step 6: The installation is complete. Click "Promote this server to a domain controller".
![Server Manager](/images/test7.png)

Step 7: In the Deploy Configuration pop-up window, select Add a new forest, enter the root domain name, and then click Next. In this example, the new forest is mycompany.local.
![Server Manager](/images/test8.png)

Step 8: In Domain Controller Selection, enter the custom password, then click Next.
![Server Manager](/images/test9.png)

Step 9: Click Next in DNS Options.
![Server Manager](/images/test10.png)

Step10: In Other Options, click Next.
![Server Manager](/images/test11.png)

Step 11: Leave the default settings in Paths, then click Next.
![Server Manager](/images/test12.png)

Step 12: In Review Options, review and confirm the information, then click Next. Optionally, save the PowerShell script if you want to automate this task in another environment.
![Server Manager](/images/test13.png)

Step 13: After the Prerequisites Check completes, click Install.
![Server Manager](/images/test14.png)

Step 14: When the installation is complete, the system will automatically restart to apply the Active Directory configuration.
![Server Manager](/images/test15.png)



### Create user and group accounts

Step 1: Create two user groups: HWC-ADFSAdmin and HWC-ADFSGuest. Open the Active Directory Administrative Center from Management Tools.
![UC](/images/ADUC1.png)
![UC](/images/ADUC2.png)






### Domain-Joined Client
![Domain Join](screenshots/active-directory/domain-join.png)

