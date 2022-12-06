<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Account
- Active Microsoft Azure Subscription
- osTicket installation software

<h2>Installation Steps</h2>
<p>
Before we begin, here is a link to the files you will need in order to install osTicket. I will be refering to this in the tutorial.

Link: https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Resource Group and create a Virtual Machine (VM) with 2-4 Virtual CPUs. I used Windows 10 as my operating system. Make sure to allow the VM to create a new Virtual Network (Vnet). 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Connect to your VM with Remote Desktop. Once you are in, install and enable Internet Information Services (IIS). To do this, go to your Control Panel, then click on "Uninstall or change programs". From here, click on "Turn Windows features on or off" on the left side of the screen. Scroll down to IIS and check the box next to it. Now click OK. Now you can install IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install Web Platform Installer from the link above. Once installed, add the programs listed in the photo above. When you add MySQL 5.5, it will ask you for credential to be created later. I used "root" as the name and "Password1" as the password.

There will be programs that failed to install. They will be in the installation files link in the beginning. The files you want to install are PHP Version 7.3.8, PHP Manager 1.5.0 for IIS 10 and Microsoft Visual C++ 2009 Redistributable Package(vcredist_x86.exe). 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install Web Platform Installer from the link above. Once installed, add the programs listed in the photo above. When you add MySQL 5.5, it will ask you for credential to be created later. I used "root" as the name and "Password1" as the password.

There will be programs that failed to install. They will be in the installation files link in the beginning. The files you want to install are PHP Version 7.3.8, PHP Manager 1.5.0 for IIS 10 and Microsoft Visual C++ 2009 Redistributable Package(vcredist_x86.exe). 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />
