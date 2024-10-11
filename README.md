# Managing-Access-Controls-in-Windows-Server

## Objective

The objective of this lab was to practice managing Active Directory (AD), creating organizational units (OUs), adding users and computers, and configuring Group Policy Objects (GPOs) to enforce security policies across a Windows domain.


### Skills Learned

- Understanding Active Directory and its structure
- Creating and managing **Organizational Units (OUs)** and user accounts
- Configuring and applying **Group Policy Objects (GPOs)** for security
- Retrieving information from AD using **PowerShell**
- Managing domain-wide security settings, including password policies
- Creating security groups and computer objects
- Interacting with PowerShell for AD management and reporting

### Tools Used

- **Azure Virtual Machine.**
- **Windows Server Manager** to manage Active Directory and GPOs.
- **Active Directory Users and Computers Tool** for creating and managing users, groups, and organizational units.
- **PowerShell** for retrieving information from Active Directory, creating objects, and generating security reports.
- **Group Policy Management Tool** for creating, editing, and enforcing GPOs across domain environments.

## Steps
**1.Logged into Domain Controller**
First, I logged into the Domain Controller where our Active Directory (AD) resides.

**2.Verified User Details in PowerShell**
I opened PowerShell as an administrator to retrieve user details using the whoami command. This provided the Security Identifier (SID) of the current user, along with the Distinguished Name (DN), which helps identify the user’s exact location in the AD hierarchy.

**3.Exploring Active Directory Users and Computers** 
I accessed Active Directory Users and Computers via Server Manager. From there, I expanded the domain and created a new Organizational Unit (OU) named "IT Admins." This would allow me to better manage different users and computers.

**4.Creating a User in Active Directory**
Inside the newly created "IT Admins" OU, I added a new user, setting their first name, last name, and login credentials. After creating the user, I was able to see them listed in the OU, which was now ready for management.

**5.Creating a Security Group**
I created a new security group called "Desktop Support" within the same OU. This group would allow me to assign security settings and policies more easily to users and devices that belong to this group.

**6.Adding a Computer Object in AD**
I added a computer object named "Laptop01" within the domain using PowerShell. To verify, I generated a list of computers in AD and exported the results to a file on the C: drive. I confirmed the presence of "Laptop01" in the exported file.

**7.Configuring Group Policy Objects (GPOs)** I then moved to the Group Policy Management Console (GPMC). Within the Default Domain Policy, I configured several password policies:

Minimum password length: 14 characters

Maximum password age: 90 days

Minimum password age: 1 day

Password history: 20 passwords

Reversible encryption: Disabled
This ensured that the security standards for user accounts in the domain met strict requirements.

**8.Generating a GPO Report in PowerShell**
After setting the GPOs, I used PowerShell to generate a report of the changes, saving the file as HTML on the C: drive. I confirmed the new password policies were successfully applied and viewed the report to ensure everything was in order.
