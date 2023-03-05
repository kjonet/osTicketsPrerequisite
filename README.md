<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial will walk you through the pre-requisistes required to install osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files 
- Heidi SQL


<h2> Configuring osTicket- Pre-installation </h2>

This tutorial will walk you through the prerequisites required to install osTicket.

To configure the installation, we’ll be using a series of files that will need to be downloaded from here: https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h3>Step 1:</h3>

<p>Enable IIS (Internet Information Systems) through the programs applet within the control panel. Once there, click “Turn Windows features on or off”. Locat IIS, then locate and expand the Application Development Features that are nested in the World Wide Web services and select CGI. CGI is what will enable osTicket to operate off of PHP. 
Once ISS is enabled, we can test this feature by typing in the loopback address 127.0.0.1 in the browser window. If you see the IIS home base, that is an indication the web server is running. </p>

<a href="https://imgur.com/p059b86"><img src="https://i.imgur.com/p059b86.png" title="source: imgur.com" /></a>

</br>

<h3>Step 2:</h3>
<p>Download and install PHP manager and the rewrite module named “rewrite_amd64_en-US.msi.” The rewrite module will make redirecting URLs easier for the webserver while the PHP manager will help manage PHP settings needed to operate osTicket. 
Next, download the PHP program files, named, “php-7.3.8-nts-Win32-VC15-x86.zip”
Once downloaded, create a new directory named “PHP” on your C: drive. 
Extract the contents of the zipped “php-7.3.8-nts-Win32-VC15-x86.zip” file and direct its continents to the newly created PHP folder. </p>

<a href="https://imgur.com/wiv0kkK"><img src="https://i.imgur.com/wiv0kkK.png" title="source: imgur.com" /></a>

</br>

<h3>Step 3:</h3>

<p>Download and install the rewrite module file named, “rewrite_amd64_en-US.msi”
Next, download and install the C++ file named, “VC_redist.x86.exe”</p>

</br>

<h3>Step 4: </h3>

<p>Next, download and install MySQL. This will be the database needed to store all the user data that will be created and used within osTicket. 
During the installation of osTicket, you’ll want to select “Typical Setup”. After the installation, you’ll want to launch the configuration wizard, select standard configuration and create a password. </p>

</br>

<h3>Step 5: </h3>

<p>Go down to the search bar and open up IIS and run as an admin. To do that, right click on the service and select “Run as administrator”. Once on the home page, navigate to “PHP manager” 
 </br>
    <a href="https://imgur.com/QfLFxCr"><img src="https://i.imgur.com/QfLFxCr.png" title="source: imgur.com" /></a>
 </br>
Inside the PHP Manager, you’ll need to select “Register PHP”, once open, navigate to the PHP folder we created in the C: drive earlier and select the “php-cgi” executable. </p>
</br>
<a href="https://imgur.com/Lu71So0"><img src="https://i.imgur.com/Lu71So0.png" title="source: imgur.com" /></a>
</br>
<a href="https://imgur.com/GuVg33p"><img src="https://i.imgur.com/GuVg33p.png" title="source: imgur.com" /></a>
</br>
<p>Restart the web server </p>


<h3> Step 6: </h3>

<p> Download OS ticket. Once downloaded, navigate to the OS ticket folder where it says “upload”. Extract and copy that folder over to “wwwroot” folder located in the C: drive. Path: C:\inetpub\wwwroot. Once the uploads folder has been placed inside, change rename the folder to “osTicket” </p>

</br>
<a href="https://imgur.com/vdPfDq4"><img src="https://i.imgur.com/vdPfDq4.png" title="source: imgur.com" /></a>


</br>

<h3>Step 7: </h3>

<p>Go back to IIS, over in the left hand corner, navigat through the folders until you see the “osTicket”  folder. Once there, over on the right, click, “Browse *80” osTicket should load in the browser. You should be directed to osTicket in your browser. </p>

</br>
<a href="https://imgur.com/t0v2XOC"><img src="https://i.imgur.com/t0v2XOC.png" title="source: imgur.com" /></a>

<p>There are a few extensions we’ll need to enable. To do that, head back over to IIS, and select the PHP manager. Scroll to the bottom until you see “Enable or disable extensions” click it and enable the following:</p>
</br>
<p>
    - php_imap.dill </br>
    - php_intl. dill </br>
    - php_opcache. dill </br>
</p>
<p>Refresh the ticketing site and observe the changes.</p>

<h3>Step 8:</h3>

<p>Navigate to the From: osTicket folder in the “wwwroot” folder and change the name of the “ost-sampleconfig.php” file to just “ost-config.php” 
Right click on the file and enable permissions by disabling inheritance and adding full control to everyone in the VM for now. </p>

</br>

<h3>Step 9:</h3>

<p> Continue setting up osTicket in the browser. 
Go back to the installation files and download Heidi SQL. Heidi SQL will allow us to connect to the SQL server, enabling us to set up a database. 
Once installed, select “New” over in the bottom left corner and use the same credentials created when setting up My SQL. Within Heidi SQL, create a new database named “osTicket”. 
Back in the osTicket browser, at the bottom where you’ll find the database settings. Add the name of the database and log in credentials. </p>

</br>

<h3>Step 10:</h3>

<p>For clean up, go into the osTicket folder located in the wwwroot folder and delete the “setup” folder. 
Navigate to the “include” folder over in the osTicket folder and change file permissions from having full control to just read & execute permissions. </p>

</br>

<p>This completes the initial installation of osTicket! </p>

<a href="https://imgur.com/Bw3ykc6"><img src="https://i.imgur.com/Bw3ykc6.png" title="source: imgur.com" /></a>
