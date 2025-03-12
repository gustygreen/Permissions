<p align="center">
<img src="https://github.com/user-attachments/assets/3e954d94-4ad7-4a5d-bf7f-8daac0f3a899"  height="30%" width="30%"/>
</p>

<h1>Security Groups and Permissions</h1>
In this lab, we will explore and experiment with how Security Groups are setup. In this exercise, the goal is to enhance our knowledge of how permissions for Security Groups function.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2) - Client 1
- Windows Server - DC-1(Domain Controller)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Virtual Network inside Azure Resource Group

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/user-attachments/assets/70f2f67d-7876-4788-9802-a6119c9efd16" height="50%" width="50%"/>
</p>

<p>
Create a Resource Group, as seen in the lab [Creating Virtual Machines within Azure](https://github.com/gustygreen/Azure). Create and add a Virtual Network. Create and add the Domain Controller. Create and add the Client.
Create users on the DC.
<br />
<p>

  
<h2>Lab Steps</h2>
<h3>Create Security Group(ex: Accountants)</h3>
<p>
<img src="https://github.com/user-attachments/assets/664e00e9-4878-4e24-915d-eff2e92d58ae" heigth="50%" width="50%"/>

<img src="https://github.com/user-attachments/assets/a3f49e11-fb46-42de-b971-899b4e7406ec" heigth="50%" width="50%"/>
</p>
<p>
On Domain Controller(dc-1) create Accpountants Security Group. Go to Active Directory Users and Computers, Right click mydomain.com(1)-Select New(2)-Organizational Unit(3), Create _GROUPS folder. Select OK
</p>

<p>
<img src="https://github.com/user-attachments/assets/a4476034-194c-4bf4-b6ac-da86c31f81a6" heigth="50%" width="50%"/>

<img src="https://github.com/user-attachments/assets/ec4557e9-4fbd-42e1-b8c4-3fc71482f239" heigth="50%" width="50%"/>
</p>
<p>
Right click _GROUPS(1). Select New(2). Select Group(3). Add Group name: ACCOUNTANTS. Default Group Scope:Global and Group Type:Security. Select OK 
</p>
<p>
<img src="https://github.com/user-attachments/assets/306c80ae-2e2e-4882-ac9f-a267f4cdab44" heigth="50%" width="50%"/>
</p>
<p>
Give ACCOUNTANTS access to read/write to the finance folder that is created on the c:\windows drive. RIght click finance-Properties-Sharing-Share-Type name "ACCOUNTANTS". Select Add.
</p>

<p>
<img src="https://github.com/user-attachments/assets/ee5d099f-077a-4dbb-a30b-c0f6dfca779c" heigth="50%" width="50%"/>  
</p>
<p>
Change Permission Level to Read/Write. Select Share.  
</p>

<p>
<img src="https://github.com/user-attachments/assets/4a69fe5b-6394-4145-b0cd-094ca5dad9b0" heigth="50%" width="50%"/>
</p>
<p>
Message will display that the file is now shared.
</p>

<h3>Place a user in the ACCOUNTANTS Group</h3>

<p>
<img src="https://github.com/user-attachments/assets/cc840559-772b-4bc1-b7cd-7f1e677b55ab" heigth="50%" width="50%"/>
</p>
<p>
On dc-1 go to Active Directory Users and Computers, select Employee to place in the ACCOUNTANTS Group, Right click on the employee, select "Add to a group...".
</p>

<p>
<img src="https://github.com/user-attachments/assets/6fdf3d50-4a5d-4849-a697-8169a1c30aab" heigth="50%" width="50%"/>
</p>
<p>
Enter "ACCOUNTANTS" in the object name field(1). Select "Check Names" to verify the group exists(2). Select OK(3). A popup will display that the Group add operation was completed.
</p>

<h3>Access finance folder with an Accountant and a non-Accountant employee.</h3>

<p>
<img src="https://github.com/user-attachments/assets/7d9e3eda-31d2-4c90-9289-d537c3587f11" heigth="50%" width="50%"/>
</p>
<p>
On client-1, as an Accountant employee when accessing the finance folder the user should have permission to read/write.
</p>

<p>
<img src="https://github.com/user-attachments/assets/ec94245c-3933-4d1a-8729-03f0f3d3ee47" heigth="50%" width="50%"/>
</p>
<p>
On client-1, as a non-accountant employee when accessing the finance folder the user should get a Network permission request denied message.
</p>

This concludes the lab on Security Groups and Permissions.
