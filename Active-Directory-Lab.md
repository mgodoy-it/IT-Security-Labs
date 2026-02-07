# Active Directory Lab – User & Group Management

## Objective
Install Active Directory Domain Services (AD DS), promote a server to a Domain Controller, create users and groups, and manage group membership in a lab environment.

## Install Active Directory Domain Services

1. Open **Server Manager** → Click **Add Roles and Features**  
2. Select **Role-based or feature-based installation** → Click **Next**  
3. Select the **Server** from the Server Pool → Click **Next**  
4. From the **Roles** list, select **Active Directory Domain Services** → Click **Next**  
5. Confirm installation → Click **Install**  
6. After installation completes, click **Promote this server to a domain controller**  

### Promote Domain Controller
7. In the **Deploy Configuration** pop-up, select **Add a new forest** → Enter the **Root Domain Name** (e.g., `mycompany.local`) → Click **Next**  
8. In **Domain Controller Options**, set a **DSRM password** → Click **Next**  
9. Click **Next** in **DNS Options**  
10. Click **Next** in **Additional Options**  
11. Leave default **Paths** → Click **Next**  
12. Review all settings → Optionally save **PowerShell script** → Click **Next**  
13. After the **Prerequisites Check** completes → Click **Install**  
14. The server will automatically **restart** to complete AD configuration  

## Create Users and Groups

1. Open **Active Directory Administrative Center (ADAC)** from **Management Tools**  
2. Create **two security groups**:  
   - `HWC-ADFSAdmin`  
   - `HWC-ADFSGuest`  
3. Create **two users**:  
   - `John`  
   - `Daenerys`  
4. Add users to their respective groups:  
   - John → HWC-ADFSAdmin  
   - Daenerys → HWC-ADFSGuest  

## Notes
- Lab performed in an isolated, non-production environment  
- No real user data or credentials were used  
- Groups and users can later be used to test permissions and access control

## Skills Demonstrated
- Active Directory fundamentals  
- Identity and Access Management (IAM)  
- User and group administration  
- Basic troubleshooting

  

## Installing Active Directory in Windows Server 


### Active Directory Users & Groups

Step 1: Go to Server manager and click on Add roles and Features

![Server Manager](/images/test1.png)


Step 2: Select the Role based Installation and Select “Next”

![Server Manager](/images/test2.png)


Step 3: Select the Server from Server Pool

![Server Manager](/images/test3.png)

Step 4: Select the Active Directory Domain Services feature

![Server Manager](/images/test4.png)

Then check Active Directory Domain Services in Server Roles, and click Add Features by default in the pop-up window to install active Directory Domain Services

![Server Manager](/images/test5.png)

Step 5: Confirm page > Click on “Install”

![Server Manager](/images/test6.png)

Step 6: The installation is complete. Click "Promote this server to a domain controller"

![Server Manager](/images/test7.png)

Step 7: In the Deploy Configuration pop-up window, select Add a new forest, enter the root domain name, and then click Next. In this example, the new forest is mycompany.local

![Server Manager](/images/test8.png)

Step 8: In Domain Controller Selection, enter the custom password, then click Next

![Server Manager](/images/test9.png)


Step 9: Click Next in DNS Options

![Server Manager](/images/test10.png)

Step10: In Other Options, click Next

![Server Manager](/images/test11.png)

Step 11: Leave the default settings in Paths, then click Next

![Server Manager](/images/test12.png)

Step 12: In Review Options, review and confirm the information, then click Next. Optionally, save the PowerShell script if you want to automate this task in another environment

![Server Manager](/images/test13.png)

Step 13: After the Prerequisites Check completes, click Install

![Server Manager](/images/test14.png)

Step 14: When the installation is complete, the system will automatically restart to apply the Active Directory configuration

![Server Manager](/images/test15.png)



### Create user and group accounts

Step 1: Create two user groups: HWC-ADFSAdmin and HWC-ADFSGuest. Open the Active Directory Administrative Center from Management Tools.

![UC](/images/ADUC1.png)
![UC](/images/ADUC2.png)

Step 2: Create two users: John and Daenerys.

![UC](/images/ADUC3.png)
![UC](/images/ADUC4.png)

Step 3: Add the users to their respective groups.

![UC](/images/ADUC5.png)

Step 4: Finish the Active Directory installation.



