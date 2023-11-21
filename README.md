<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Folder Permissions</h1>
This tutorial will quickly outline network security groups and setting permissions for folders. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>High-Level Steps</h2>

- Create Folders
- Create Groups
- Assign Permissions
- Test

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To begin, log into Active Directory using the admin profile as shown in the Active Directory tutorial.

Once in, we’re going to be creating four folders: Read-Access, Write-Access, No-Access, and Accounting. The names are not important, but for the sake of this tutorial I have decided to name them based on the permissions they will be assigned.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After you’ve made the folders, right click each one and change the properties of the folder. Under the sharing tab add Domain users and set their permissions. They should be as follows:

Read-Accesss > Read 

Write-Access > Read/Write

No-Access > Domain Admins Read/Write

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The accounting folder will be able to be accessed by a new security group named Accountants. Within Active Directory, create the group and add a user profile to the group.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Add the newly created Accountants group to the Accounting folder with the permissions Read/Write.

Once all of these steps are done, log into a VM that is added to your Active Directory server with a non admin user. Test to see which folders you are able to view/edit.

</p>
<br />
