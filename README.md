# osticket-prereqs
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

- Create Virtual Machine in Azure
- Install Web Platform Installer
- Install osTicket v1.15.8
- Install HeidiSQL

<h2>Installation Steps</h2>
<h3 align="center">Create Virutal Machine in Azure</h3>
<p>
	<h4>Create a Resource Group</h4>
	<img src="https://i.imgur.com/fH0JTUb.png" height="75%" width="100%" alt="Resource Group"/>
	<h4>Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs</h4>
	When creating the VM, allow it to create a new Virtual Network (Vnet):
	<img src="https://i.imgur.com/vHQGjuQ.png" height="75%" width="100%" alt="Windows Virutal Machine"/>
</p>
<br />
<h3 align="center">Connect to your Virtual Machine with Remote Desktop</h3>
<p>
	<h4>Obtain/copy VM's public IP address. Then open Remote Desktop and type-in/paste VM's public IP address.</h4>
	<img src="https://i.imgur.com/J4WnDUj.png" height="75%" width="100%" alt="VM Public IP address"/>
	<img src="https://i.imgur.com/1KOYaCs.png" height="75%" width="100%" alt="Remote Desktop"/>
</p>
<br />
<h3 align="center">Install / Enable IIS in Windows with CGI</h3>
<p>
	<h4>Navigate to "Control Panel" > "Programs" > "Turn Windows features on or off" inside the VM</h4>
	<img src="https://i.imgur.com/Wx1YwTr.png" height="75%" width="100%" alt="Control Panel-Programs"/>
	<h4>In the "Turn Windows features on or off" window, navigate to IIS (turn on) > Worl Wide Web Services > Application Development features > CGI (turn on). Under Worl Wide Web Services branch, navigate to Common HTTP Features and ensure all selections are marked then click "Ok".</h4>
	<img src="https://i.imgur.com/Nb212NQ.png" height="75%" width="100%" alt="Turn Windows Features on/off"/>
</p>
<br />
<h3 align="center">Install Web Platform Installer</h3>
<p>
	<h4>Download and Install PHP Manager for IIS</h4>
	<img src="https://i.imgur.com/ZRTCdhu.png" height="75%" width="100%" alt="PHP Manager"/>
	<h4>Download and Install IIS URL Rewrite Module 2</h4>
	<img src="https://i.imgur.com/noTYicL.png" height="75%" width="100%" alt="IIS URL Rewrite"/>
	<h4>Create "PHP" folder in VM's (C:) drive</h4>
	<img src="https://i.imgur.com/rW6RKTK.png" height="75%" width="100%" alt="PHP Folder"/>
        <h4>Download and install PHP Version 7.3.8 (or any other version if necessary, archives). Extract all files to VM's C:\PHP</h4>
	<img src="https://i.imgur.com/v5oDxYs.png" height="75%" width="100%" alt="PHP Extracted Files"/>
	<h4>Download and install Microsoft Visual C++</h4>
	<img src="https://i.imgur.com/0LXcAMW.png" height="75%" width="100%" alt="Microsoft Visual C++"/>
	<h4>Download and Install MySQL</h4>
</p>
<p>
  Open after installation:
</p>
<p>
	<!<img src="https://i.imgur.com/X0GcGff.png" height="75%" width="100%" alt="MySQL 5.5"/>>
</p>
<br />
<p>
  Add MySQL 5.5 (it will ask for credentials to be created later).
</p>
<p>
  Name: root
</p>
<o>
  Password: Password1:
</p>
<p>
	<!<img src="https://i.imgur.com/zdhWXNx.png" height="75%" width="100%" alt="Credentials"/>>
</p>
<p>
  Add All simple versions of x86 PHP up until 7.3:
</p>
<p>
	<!<img src="https://i.imgur.com/0npbiTj.png" height="75%" width="100%" alt="PHP"/>>
</p>
<p>
  Fix any failures if required. 
</p>
<p>
  Install PHP Version 7.3.8 (or any other version if necessary, archives).
</p>
<p>
  Install Microsoft Visual C++ 2009 Redistributable Package (if necessary).
</p>
<p>
  Install PHP Manager 1.5.0 for IIS 10:
</p>
<p>
	<!<img src="https://i.imgur.com/LcD8jGJ.png" height="75%" width="100%" alt="PHP Manager"/>>
</p>
<br />
<br />
<h3 align="center">Install osTicket v1.15.8</h3>
<br />
<p>
  Download osTicket (download from within lab files: link).
</p>
<p>
	Extract and copy the “upload” folder INTO c:\inetpub\wwwroot:
</p>
	<!<img src="https://i.imgur.com/0MUJLMU.png" height="75%" width="100%" alt="PHP Manager"/>>
	<!<img src="https://i.imgur.com/1h9goM8.png" height="75%" width="100%" alt="PHP Manager"/>>
<p>
	Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”:
</p>
<p>
	<!<img src="https://i.imgur.com/pDikkgq.png" height="75%" width="100%" alt="rename to osTicket"/>>
</p>
<br />
<br />
<h3 align="center">Reload IIS (Open IIS, Stop and Start the server)</h3>
<br />
<p>
	Go to sites -> Default -> osTicket:
</p>
<p>
	<!<img src="https://i.imgur.com/QeWNlG3.png" height="75%" width="100%" alt="default osTicket"/>>
</p>
<p>
	On the right, click “Browse *:80”:
</p>
<p>
	<!<img src="https://i.imgur.com/3iXhNbi.png" height="75%" width="100%" alt="port 80"/>>
</p>
<br />
<br />
<h3 align="center">Enable Extensions in IIS: Note that some extensions are not enabled</h3>
<br />
<p>
	Go back to IIS, sites -> Default -> osTicket.
</p>
<p>
	Double-click PHP Manager:
</p>
<p>
	<!<img src="https://i.imgur.com/LFKo5Hs.png" height="75%" width="100%" alt="PHP Manager"/>>
</p>
<p>
	Click “Enable or disable an extension”.
</p>
<p>
	Enable: php_imap.dll.
</p>
<p>
	Enable: php_intl.dll.
</p>
<p>
	Enable: php_opcache.dll:
</p>
<p>
	<!<img src="https://imgur.com/a/nrQo0kz" height="75%" width="100%" alt="Disk Sanitization Steps"/>>
</p>
<br />
<br />
<h3 align="center">Refresh the osTicket site in your browser, observe the changes</h3>
<br />
<p>
	<!<img src="https://i.imgur.com/6iSNd4H.png" height="75%" width="100%" alt="osTicket change"/>>
</p>
<br />
<br />
<h3 align="center">Rename</h3>
<br />
<p>
	From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php.
</p>
<p>
	To: C:\inetpub\wwwroot\osTicket\include\ost-config.php:
</p>
<p>
	<!<img src="https://i.imgur.com/TEw71SD.png" height="75%" width="100%" alt="ost-config"/>>
</p>
<br />
<br />
<h3 align="center">Assign Permissions: ost-config.php</h3>
<br />
<p>
	Disable inheritance -> Remove All:
</p>
<p>
	<!<img src="https://i.imgur.com/1QtRWEF.png" height="75%" width="100%" alt="disable inheritance"/>>
</p>
<p>
	New Permissions -> Everyone -> All:
</p>
<p>
	<!<img src="https://i.imgur.com/YzsMXNX.png" height="75%" width="100%" alt="new permissions"/>>
</p>
<p>
	<!<img src="https://i.imgur.com/k7x9yGR.png" height="75%" width="100%" alt="new permissions - all"/>>
</p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser (click Continue)</h3>
<br />
<p>
	Name Helpdesk.
</p>
<p>
	Default email (receives email from customers):
</p>
<p>
	<!<img src="https://i.imgur.com/rvMvlNC.png" height="75%" width="100%" alt="continue osTicket setup"/>>
	<!<img src="https://i.imgur.com/YszhIpl.png" height="75%" width="100%" alt="osTicket settings"/>>
</p>
<br />
<br />
<h3 align="center">Download and Install HeidiSQL</h3>
<br />
<p>
	<!<img src="https://i.imgur.com/AEg0b2P.png" height="75%" width="100%" alt="download HeidiSQL"/>>
</p>
<p>
	Create a new session, root/Password1.
</p>
<p>
	Connect to the session:
</p>
<p>
	<!<img src="https://i.imgur.com/9t51ApR.png" height="75%" width="100%" alt="create sessions"/>>
</p>
<p>
	Create a database called “osTicket”:
</p>
<p>
	<!<img src="https://i.imgur.com/vXzmQqg.png" height="75%" width="100%" alt="create database"/>>
</p>
<br />
<br />
<h3 align="center">Continue Setting up osTicket in the browser</h3>
<br />
<p>MySQL Database: osTicket</p>
<p>
	MySQL Username: root
</p>
<p>
	MySQL Password: Password1:
</p>
<p>
	<!<img src="https://i.imgur.com/akDyber.png" height="75%" width="100%" alt="setting up osTicket cont'd"/>>
</p>
<p>Click “Install Now!”</p>
<p>Congratulations, hopefully it is installed with no errors!</hp>
<p>
	<!<img src="https://i.imgur.com/J5omRoE.png" height="75%" width="100%" alt="installation complete"/>>
</p>
<br />
<br />
<h3 align="center">Clean up</h3>
<br />
<p>
	Delete: C:\inetpub\wwwroot\osTicket\setup:
</p>
<p>
	<!<img src="https://i.imgur.com/eg0ZPG3.png" height="75%" width="100%" alt="clean up"/>>
</p>
<p>
	Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php:
</p>
<p>
	<!<img src="https://i.imgur.com/n6k46XL.png" height="75%" width="100%" alt="permissions"/>>
</p>
<br />
<br />
<h3 align="center">Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)</h3>
<br />
<p>
	<!<img src="https://i.imgur.com/zklvv8K.png" height="75%" width="100%" alt="admin panel"/>>
</p>
<br />
<br />
<p>
	And there you have it! I hope this tutorial helped you with installing osTicket.
</p>
<p>
	And now you can practice having your own mock help desk locally to prepare you for a postion in a help desk or IT support position.
</p>
