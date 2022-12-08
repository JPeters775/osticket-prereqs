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

- Windows 10 Pro version 21H2 - Gen 2</b> 

<h2>List of Prerequisites</h2>

- Microsoft Azure Account
- Active Microsoft Azure Subscription
- osTicket installation software

<h2>Installation Steps</h2>
<p>
Before we begin, here is a link to the files you will need in order to install osTicket. I will be refering to this in the tutorial.

<a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> Installation Files for osTicket</a>
</p>
<br />
<p>
<img src="https://i.imgur.com/NUnaVEq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Create Virtual Machine in Azure</h3>

<p>
Create a Resource Group and create a Virtual Machine (VM) with 2-4 Virtual CPUs. I used Windows 10 as my operating system. Make sure to allow the VM to create a new Virtual Network (Vnet). 
</p>
<br />

<p>
<img src="https://i.imgur.com/e73100y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Install/Enable Internet Installation Services (IIS)</h3>

<p>
Connect to your VM with Remote Desktop. Once you are in, install and enable Internet Information Services (IIS). To do this, go to your Control Panel, then click on "Uninstall or change programs". From here, click on "Turn Windows features on or off" on the left side of the screen. Scroll down to IIS and check the box next to it. Now click OK. Now you can install IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/OOP2bV4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Install Web Platform Installer</h3>

<p>
Install Web Platform Installer from this <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> link</a>. Once installed, add the programs listed in the photo above. When you add MySQL 5.5, it will ask you for credential to be created later. I used "root" as the name and "Password1" as the password.

There will be programs that failed to install. They will be in the installation files <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> link</a>. The files you want to install are PHP Version 7.3.8, PHP Manager 1.5.0 for IIS 10 and Microsoft Visual C++ 2009 Redistributable Package(vcredist_x86.exe). 
</p>
<br />

<p>
<img src="https://i.imgur.com/CiHsqQb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Install osTicket</h3>

<p>
Download osTicket from this <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> link</a>. Extract the osTicket folder. Inside the osTicket folder find the "upload" folder. Copy the "upload" folder. Paste it into "c:\inetpub\wwwroot". Now, rename that copied "upload" folder to "osTicket"
</p>
<br />

<p>
<img src="https://i.imgur.com/GmA0emx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Open IIS, Stop and Start the server</h3>

<p>
Open the IIS application. On the leftside of the IIS, you will see the pulldown with the name of your VM. Go to "Sites" -> "Default Web Site -> osTicket.

Next, on the right of the screen, click "Browse *:80”. This will bring you to the webpage of osTicket. You will see that a few extensions are needed to continue. We'll go over that next.
</p>
<br />

<p>
<img src="https://i.imgur.com/bAnjFrF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Enable Extensions in IIS</h3>

<p>
Go back to IIS and the osTicket folder. Now, double-click PHP Manager, then click "Enable of disable an extension". Enable these extensions:
- php_imap.dll
- php_intl.dll
- php_opcache.dll

Once this is finished, go back to osTicket webpage, refresh and observe the changes. You should see that Intl Extension now has a green checkmark.
</p>
<br />

<p>
<img src="https://i.imgur.com/qcUOyg3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Assigning Permissions</h3>

<p>
We need to rename a php file. Go to the "osTicket" folder, then the "include" folder. Inside the "include" folder, there will be a file named "ost-sampleconfig.php". Rename that folder to "ost-config.php".
  
<p>
<img src="https://i.imgur.com/jsAiLmL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Now, we will assign the permissions. Right click "ost-config.php" and click on Properties. Next, go to Security, then Advanced. Disable inheritances and remove all inheritances. Then, click Add to add new permissions. Click select a principal. Enter object name as "Everyone" to create the principal. Now, allow "Everyone" all of the permissions listed. Click OK and you are finished with this step. 
</p>
<br />

<p>
<img src="https://i.imgur.com/sk0aE91.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Continue Setting up osTicket in the browser</h3>

<p>
Go back to the osTicket browser and click "Continue". You will now be able to set up the Helpdesk name, email and data base. For now, create the name and email (this can be made-up).
</p>
<br />

<p>
<img src="https://i.imgur.com/d2RVWUN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Download and Install HeidiSQL</h3>

<p>
Download and install HeidiSQL from this <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> link</a>. After it is installed and downloaded, create a new session using the name and password we used earlier in the Web Platform Installer (Name=root Password=Password1). Connect to the session and create the database by right clicking the "Unnamed" folder on the left and then clicking "Create new database". Make sure to call it "osticket".
</p>
<br />

<p>
<img src="https://i.imgur.com/QnAlBvX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Continue Setting up osTicket</h3>

<p>
Go back to the web browser and finish completing the Basic Installation information. Create a username, password and email address for osTicket. Make sure you remember this for later use. Enter osTicket as the SQL database we just created and the username and password for the database (root/password1). You can now click "Install Now". You should now see a congratulations screen if it installed successfully with no errors.
</p>
<br />

<p>
<img src="https://i.imgur.com/qcUOyg3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>Last Step Before Starting</h3>

<p>
We will need to delete a file before continuing. Got the "osTicket" folder and delete the setup folder. You may need to go in the folder and delete all files before deleting the folder itself.

Next, go to "ost-config.php" file we changed earlier. Set the permissions from All permissions allowed to "Read" only.

Finally, we can now use osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/55XeXSc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>In Conclusion</h3>

<p>
You can now login to osTicket using the username and password you created during the installation process. To login in to your helpdesk, go to http://localhost/osTicket/scp/login.php. End users can go to http://localhost/osTicket/ to submit their tickets. 

Thank you for reading my guide! I hope this helped you.
</p>
<br />
