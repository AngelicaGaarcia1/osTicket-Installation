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

•Click start -> Search control panel -> Select programs -> Under Programs and Features select Turn windows features on or off -> Find Internet Information Services and check the box -> Now click the plus sign next to internet information services -> Click the plus sign next to World Wide Web Services -> Find Application development features and click the plus sign next to it and enable CGI (this allows us to install PHP).

•You can double check that IIS was properly installed by typing the loopback address 127.0.0.1 into the browser and you should see a page that says Internet Information Services.

</p>
<br />

<h4>STEP 3</h3>

<p>
<img src="https://i.imgur.com/zyA90gd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
•Now we need to install PHP (a backend web programming language) because osTicket runs off of PHP.
 
•Download PHPManagerForIIS_V1 5.0. msg -> Open the File and install.
 
</p>
<br />

<h4>STEP 4 </h3>

<p>
<img src="https://i.imgur.com/PvLvtck.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
•Now lets download and install the rewrite module.
</p>
<br />
<h4>STEP 5 </h3>

<p>
<img src="https://i.imgur.com/tW3xEKB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

 •Now let’s create a directory for PHP on the local hard drive. We will create a folder for PHP on the root of the Cdrive.

•Click start -> type in “This PC” and select it -> Click on Windows (C:) -> Create a folder here and name it: PHP.
</p>
<br />
<h4>STEP 6 </h3>

<p>
<img src="https://i.imgur.com/GzNbCxQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

 •Download PHP 7.3.8 and extract the contents of the php-7.3.8-nts-Win32-VC15-x86 zip into the PHP folder you created in the Cdrive.

•Click start -> type in “This PC” and select it -> Click on Windows (C:) -> Create a folder here and name it: PHP.
</p>
<br />
<h4>STEP 7 </h3>

<p>
<img src="https://i.imgur.com/lpkVM0e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

 •Download and install VC_redist.x86.exe.

</p>
<br />
<h4>STEP 8 </h3>

<p>
<img src="https://i.imgur.com/TLrhFiu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

 •Now it’s time to download MySQL which installs a database on the computer. osTicket needs somewhere to store the application data.

•When you get to “Choose Setup Type” while installing MySQL select typical.

•Continue installing...
</p>
<br />
<h4>STEP 9 </h3>

<p>
<img src="https://i.imgur.com/A96JFT2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

•Now it is going to ask you select configuration settings and you will select standard configuration. Next it is going to ask you to create a password for root. What this indicates is that your username will be root. After that, you can leave everything as is, continue and finish installing.

</p>
<br />
<h4>STEP 10 </h3>

<p>
<img src="https://i.imgur.com/TaHJ5Ol.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

•Next we will do some configuration in IIS. Go to the start menu and type in Internet Information Services and right click it to open it as an administrator. 

•Once open look for PHP manager and select it -> Click Register New PHP Version -> Browse and find the PHP folder -> Click on php.cgi

•Return to the main screen in IIS and it is strongly recommended to click restart on the web server when you make any changes.

•Now exit.

</p>
<br />
<h4>STEP 11 </h3>

<p>
<img src="https://i.imgur.com/OVxudzE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

•Now its time to install osTicket !

•First, download osTicket-v1.15.8 zip. Now open downloads and select the osTicket folder. Inside this folder you want locate the upload folder and we want to drag that into c:\inetpub/wwwroot. All this means is open your c drive [Windows (C)] in another window then select inetpub, and click on the wwwroot folder. Now drag the upload folder into the wwwroot folder.

•Now rename the upload folder to osTicket. Go back to IIS (run as admin) and restart it again.

</p>
<br />
<h4>STEP 12 </h3>

<p>
<img src="https://i.imgur.com/21m468z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

•If you go to http://localhost/osTicket/setup/ you’ll notice that there are x’s next to some extensions because they need to be enabled for you to use all features of osTicket.

•Lets go to IIS -> Select PHP Manager -> Under PHP extensions click enable or disable an extension -> enable phpimap, phpintl, and phpopache.

•Refresh ostTicket in the browser

</p>
<br />
<h4>STEP 13 </h3>

<p>
<img src="https://i.imgur.com/cc68Vls.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
•Now we want to rename the file inside of osTicket that is currently named ost-sampleconfig.php. We want to rename it to ost-config.php.

•Go to C-drive -> Select inetpub -> wwwroot -> osTicket -> Click on the include folder -> navigate to post-sampleconfig and rename it.

</p>
<br />
<h4>STEP 14 </h3>

<p>
<img src="https://i.imgur.com/NML79ID.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
•Now we want to assign permission on out-config.

•Right click on ost-config and select properties -> Select security -> select advanced -> disable inheritance -> Remove all inherited permission from this object -> Add -> Select a principal -> Inside the enter object name box type “everyone” -> Click check names and click ok -> select full control -> Apply.

</p>
<br />
<h4>STEP 15 </h3>

<p>
<img src="https://i.imgur.com/ZsGnkmB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
•Download and install HeidiSQL. Once it opens select new (on the bottom left) -> type in the root password (created when you installed MySQL).

</p>
<br />
<h4>STEP 16 </h3>

<p>
<img src="https://i.imgur.com/lv2BvvL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
•Now lets create a new database called osTicket inside of HeidiSQL.

•Right click under “unnamed” -> create new -> database -> name osTicket

</p>
<br />
<h4>STEP 17 </h3>

<p>
<img src="https://i.imgur.com/tXt7yY2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
•Now lets head back to http://localhost/osTicket/setup and complete the installation by filling in the required information.

</p>
<br />
<strong> COMPLETE
 
<p>
<img src="https://i.imgur.com/g24AZ75.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Congratulations! You have completed the installation of osTicket.

