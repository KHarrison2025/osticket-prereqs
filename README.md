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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Create a Windows 10 4vCPUs virtual machine in Microsoft Azure and log in using remote desktop
- Download and unzip the osTicket installation files within the virtual machine
-Install PHP manager for IIS
- Install the rewrite module
- Create the directory C:\PHP
- Install the Microsoft C++ Redistributable
- Install MySQL
- Open IIS as administrator and register PHP from within IIS

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/4niSguj.png"/>
</p>
<p>
The first step is to create a Windows 10 virtual machine in Microsoft Azure with 4vCPUs. Use the public IP address to connect via Remote Desktop and log in.
</p>
<br />

<p>
<img src="https://i.imgur.com/5GNUn5P.png"/>
</p>
<p>
Whilst in the virtual machine, download and unzip the osTicket installation files to the desktop.
</p>
<br />

<p>
<img src="https://i.imgur.com/hVnuX97.png"/>
</p>
<p>
<img src="https://i.imgur.com/rrgk3R5.png"/>
</p>
<p>
Enable Internet Information Services in Windows and enable CGI under World Wide Web Services and Application Development Features.
</p>
<br />

<p>
<img src="https://i.imgur.com/bwBMu5e.png"/>
</p>
<p>
Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the osTicket installation files folder on the desktop.
</p>
<br />

<p>
<img src="https://i.imgur.com/c94ysod.png"/>
</p>
<p>
  Install the Rewrite Module(rewrite_amd64_en-US.msi) from the same folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/5Xq885g.png"/>
</p>
<p>
  Create the directory "C:\PHP" and unzip PHP 7.3.8(php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/kxm4oAd.png"/>
</p>
<p>
  Install Microsoft C++ Redistributable(VC_redist.x86.exe)
</p>
<br />

<p>
<img src="https://i.imgur.com/dy7GatH.png"/>
</p>
<p>
<img src="https://imgur.com/a/h5Te2gO"/>
</p>
<p>
  Install MySQL 5.5.62(mysql-5.5.62-win32.msi) with typical setup. Automatically launch the configuration wizard after installation. Set to standard configuration. While not the safest security option, the password "root" will be used for demonstrative purposes this time.
</p>
<br />

<p>
<img src="https://i.imgur.com/ON9r7hU.png"/>
</p>
<p>
  Open IIS as Administrator. Within IIS, register PHP(PHP Manager -> C:\PHP\php-cgi.exe). Reload ISS(stop and start).
</p>
<p>
<img src="https://i.imgur.com/iP8h20f.png"/>
</p>
<p>
<img src="https://i.imgur.com/iegM0aU.png"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/j3lwfLu.png"/>
</p>
<p>
  Unzip “osTicket-v1.15.8.zip from within the osTicket installation files folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/dgM76rc.png"/>
</p>
<p>
  Copy the “upload” folder into “c:\inetpub\wwwroot”. Rename this file "osTicket". Reload IIS, by opening Internet Information Services, stopping and starting the server.
</p>
<br />

<p>
<img src="https://i.imgur.com/yCWjjxG.png"/>
</p>
<p>
  Some extensions need to be enabled. To do this go to IIS, then sites, then Default Web Site, then osTicket. Double click on "PHP Manager", then click on "Enable or disabale an extension". These three items will need to be enabled: "php_imap.dll", "php_intl.dll", and "php_opcache.dll". Once these three are enabled refresh the osTicket website notice the changes that have taken place.
</p>
<br />

<p>
<img src="https://i.imgur.com/J4m3zCI.png"/>
</p>
<p>
  C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php will need to be renamed to C:\inetpub\wwwroot\osTicket\include\ost-config.php.
</p>
<br />

<p>
<img src="https://i.imgur.com/uuCgJQj.png"/>
</p>
<p>
  Next is to assign permissions for "ost-config.php". Under "Advanced Security Settings", then "Permissions" click "Disable inheritance" and "Remove All". Click "Enable inheritance", type "Everyone" and select "Full control"
</p>
<br />

<p>
<img src="https://i.imgur.com/XMZqspV.png"/>
</p>
<p>
  Go back into the browser to fill out the basic information for setting up osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/ZjiEbPb.png"/>
</p>
<p>
  Go back to the osTicket installation files folder and install Heidi SQL. Create a new session with the username and password as "root". Connect to the session and create a database named "osTicket".
</p>
<br />

<p>
<img src="https://i.imgur.com/X9iSHP6.png"/>
</p>
<p>
  Go back to the browser to finish setting up osTicket by filling in the database settings.
</p>
<br />

<p>
<img src="https://i.imgur.com/LGAD9xn.png"/>
</p>
<p>
  Once complete with no errors, osTicket is successfully installed and ready to use!
</p>
<br />
