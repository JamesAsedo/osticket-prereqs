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
- Setup osTicket in browser
- Install HeidiSQL

<h2>Installation Steps</h2>
<h3 align="center">Create Virutal Machine in Azure</h3>
<p>
	<h4>Create a Resource Group</h4>
	<img src="https://i.imgur.com/fH0JTUb.png" height="25%" width="50%" alt="Resource Group"/>
	<h4>Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs</h4>
	When creating the VM, allow it to create a new Virtual Network (Vnet):
	<img src="https://i.imgur.com/vHQGjuQ.png" height="25%" width="50%" alt="Windows Virutal Machine"/>
</p>
<br />
<h3 align="center">Connect to your Virtual Machine with Remote Desktop</h3>
<p>
	<h4>Obtain/copy VM's public IP address. Then open Remote Desktop and type-in/paste VM's public IP address.</h4>
	<img src="https://i.imgur.com/J4WnDUj.png" height="50%" width="70%" alt="VM Public IP address"/>
	<img src="https://i.imgur.com/1KOYaCs.png" height="50%" width="70%" alt="Remote Desktop"/>
</p>
<br />
<h3 align="center">Install / Enable IIS in Windows with CGI</h3>
<p>
	<h4>Navigate to "Control Panel" > "Programs" > "Turn Windows features on or off" inside the VM</h4>
	<img src="https://i.imgur.com/Wx1YwTr.png" height="50%" width="70%" alt="Control Panel-Programs"/>
	<h4>In the "Turn Windows features on or off" window, navigate to IIS (turn on) > Worl Wide Web Services > Application Development features > CGI (turn on). Under Worl Wide Web Services branch, navigate to Common HTTP Features and ensure all selections are marked then click "Ok".</h4>
	<img src="https://i.imgur.com/Nb212NQ.png" height="50%" width="70%" alt="Turn Windows Features on/off"/>
</p>
<br />
<h3 align="center">Install Web Platform Installer</h3>
<p>
	<h4>Download and Install PHP Manager for IIS</h4>
	<img src="https://i.imgur.com/ZRTCdhu.png" height="50%" width="50%" alt="PHP Manager"/>
	<h4>Download and Install IIS URL Rewrite Module 2</h4>
	<img src="https://i.imgur.com/noTYicL.png" height="50%" width="50%" alt="IIS URL Rewrite"/>
	<h4>Create "PHP" folder in VM's (C:) drive</h4>
	<img src="https://i.imgur.com/rW6RKTK.png" height="50%" width="50%" alt="PHP Folder"/>
        <h4>Download and install PHP Version 7.3.8 (or any other version if necessary, archives). Extract all files to VM's C:\PHP</h4>
	<img src="https://i.imgur.com/v5oDxYs.png" height="50%" width="50%" alt="PHP Extracted Files"/>
	<h4>Download and install Microsoft Visual C++</h4>
	<img src="https://i.imgur.com/0LXcAMW.png" height="50%" width="50%" alt="Microsoft Visual C++"/>
	<h4>Download and Install MySQL</h4>
	<img src="https://i.imgur.com/IdeCXFb.png" height="50%" width="50%" alt="MySQL Download"/>
	<h4>Launch Configuration Wizard after MySQL downloads > Standard Configuration > Create root password</h4>
	<img src="https://i.imgur.com/D1ySEcE.png" height="50%" width="50%" alt="MySQL Configuration"/>
	<img src="https://i.imgur.com/RCs6Nd3.png" height="50%" width="50%" alt="MySQL Password Configuration"/>
	<h4>Open and Run IIS as an Admin and register PHP from within IIS</h4>
	<img src="https://i.imgur.com/8j2M09A.png" height="50%" width="50%" alt="Register PHP"/>
	<h4>Select "php-cgi" from within the C:\PHP folder</h4>
	<img src="https://i.imgur.com/Mxv8XKb.png" height="50%" width="50%" alt="Select PHP-CGI"/>
</p>
<br/>
<h3 align="center">Install osTicket</h3>
<p>
	<h4>Download and install osTicket. Extract and copy "upload" folder to C:\inetpub\wwwroot. Within C:\inetpub\wwwroot, rename "upload" to "osTicket"</h4>
	<img src="https://i.imgur.com/2rXGpHe.png" height="50%" width="50%" alt="Install osTicket"/>
	<h4>Reload/restart IIS Server > go to Sites > Default > osTicket > on the right, click "Browse *:80"</h4>
	<img src="https://i.imgur.com/Yz6WPW0.png" height="50%" width="50%" alt="Reload IIS"/>
	<img src="https://i.imgur.com/xvJ5elE.png" height="50%" width="50%" alt="Browse *:80"/>
	<h4>Navigate to osTicket from within IIS Manager > double-click PHP Manager > click "enable or disable an extension" and enable the following extensions: php_imap.dll; php_intl.dll; php_opcache.dll.</h4>
	<img src="https://i.imgur.com/NB0EsWy.png" height="50%" width="50%" alt="Navigate PHP Manager"/>
	<img src="https://i.imgur.com/REe6xp4.png" height="50%" width="50%" alt="Navigate PHP Extensions"/>
	<img src="https://i.imgur.com/07ui0xY.png" height="50%" width="50%" alt="Enable PHP Extensions"/>
	<h4>Rename C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php</h4>
	<img src="https://i.imgur.com/dZXUN4u.png" height="50%" width="50%" alt="Rename ost-config"/>
	<h4>Assign Permissions: ost-config.php > Disable inheritance: Remove All > New Permissions: Everyone -> All</h4>
	<img src="https://i.imgur.com/kdSMZHa.png" height="50%" width="50%" alt="Disable inheritance"/>
	<img src="https://i.imgur.com/y0RX0XM.png" height="50%" width="50%" alt="new permissions"/>
	<img src="https://i.imgur.com/AVfg286.png" height="50%" width="50%" alt="permissions all"/>
	<!<img src="" height="50%" width="50%" alt=""/>
	
	
</p>
<br />
<h3 align="center">Setup osTicket in Browser</h3>
<img src="https://i.imgur.com/Xof0Ude.png" height="50%" width="50%" alt="osTicket setup"/>
<p>
	<h4>Name Helpdesk and default email (receives email from customers)</h4>
	<img src="https://i.imgur.com/6Vz9pyU.png" height="50%" width="50%" alt="osTicket Helpdesk name and email"/>
	<h4>Download and Install HeidiSQL > Create new session > input previously created credentials</h4>
	<img src="https://i.imgur.com/KqEVaZe.png" height="50%" width="50%" alt="download HeidiSQL"/>
	<img src="https://i.imgur.com/gxofcVa.png" height="50%" width="50%" alt="new HeidiSQL connection"/>
	<h4>Create an "osTicket" database by right-clicking "Unnamed"-> hover to "Create new"-> click "Database"</h4>
	<img src="https://i.imgur.com/lRYfXtZ.png" height="50%" width="50%" alt="new osTicket database"/>
	<h4>Continue setting up osTicket in the browser</h4>
	<img src="https://i.imgur.com/14owS3w.png" height="50%" width="50%" alt="ocTicket Setup browser MySQL usernam and password"/>	
</p>
<br />
<h3 align="center">Cleanup</h3>
<p>
	<h4>Delete: C:\inetpub\wwwroot\osTicket\setup</h4>
	<img src="https://i.imgur.com/HRTcUbx.png" height="50%" width="50%" alt="clean up"/>
	<h4>Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</h4>
	<img src="https://i.imgur.com/OY6Viym.png" height="50%" width="50%" alt="read only permissions"/>
</p>
<br />
<h3 align="center">Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)</h3>
<img src="https://i.imgur.com/zklvv8K.png" height="50%" width="50%" alt="admin panel"/>
<br />
<p>
	And there you have it! I hope that this tutorial helped you with installing osTicket. Thank you for stopping by and checking out this tutorial. Have a wonderful day!
</p>
