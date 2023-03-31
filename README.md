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

- Windows 10 with 4 virutal CPU's </b> (21H2)


<h2>Installation Steps</h2>
<h3>STEP 1</h3>
<p>
<img src="https://i.imgur.com/ELSza07.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

•First we want to create a Windows 10 Virtual Machine with 2-4 CPU’s.
</p>
<br />
<h4>STEP 2</h3>

<p>
<img src="https://i.imgur.com/MLJy0uZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
•After the virtual machine is created we will begin the installation of osTicket by installing/ enabling IIS in windows with CGI.

•IIS stands for internet information services. It is a web server that allows the computer to host, deploy and manage web applications.

•Click start -> Search control panel -> Select programs -> Under Programs and Features select Turn windows features on or off -> Find Internet Information Services and check the box -> Now click the plus sign next to internet information services -> Click the plus sign next to World Wide Web Services -> Find Application development features and click the plus sign next to it and enable CGI (this allows us to install PHP)

•You can double check that IIS was properly installed by typing the loopback address 127.0.0.1 into the browser and you should see a page that says Internet Information Services.
</p>
<br />
<strong> STEP 3
<p>
<img src="https://i.imgur.com/zyA90gd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
•Now we need to install PHP (a backend web programming language) because osTicket runs off of PHP.

•Download PHPManagerForIIS_V1 5.0. msg -> Open the File and install
 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
