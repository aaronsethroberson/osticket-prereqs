<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Remote Desktop
- Internet Information Services (IIS)
- HeidiSQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Project Walk-through</h2>

To begin this project, we will utilize Microsoft Azure to create a Virtual Machine (VM) for building osTicket from scratch. Using a VM helps protect our personal computers from potential malfunctions or issues. In Microsoft Azure, start by creating a "Resource Group" and naming it "osTicket." Next, set up a VM with 2-4 virtual CPUs (vCPUs).
<br/>
<br/>
<img src="https://i.postimg.cc/2SF23Pdb/1.jpg" alt=""/>

<br/>
<br/>


Next, we will use Remote Desktop Protocol (RDP) to connect the newly created VM to our personal computers. Mac users should download the RDP client from the App Store before continuing.<br/>
<br/>

<img src="https://i.ibb.co/TqKgsPk/2.jpg" alt=""/>

<br/>
<br/>


Once connected to the VM, we will install and enable Internet Information Services (IIS). Start by navigating to Control Panel > Programs > Turn Windows Features On or Off. From there, enable Internet Information Services. Then, expand "World Wide Web Services," navigate to "Application Development Features," and activate CGI.
<br/>
<br/>
<img src="https://i.postimg.cc/7h0RxXxq/3.jpg" alt=""/>


<br/>
<br/>


Install PHP manager for IIS setup 
<br/>
<br/>

<img src="https://i.postimg.cc/PJHqf3m4/4.jpg" alt=""/>

<br/>
<br/>


Install IIS Rewrite Module
<br/>
<br/>


<img src="https://i.postimg.cc/GhcpZf33/5.jpg" alt=""/>

<br/>
<br/>


After the installations are complete, we will need to create a PHP directory on the C drive
<br/>
<br/>


<img src="https://i.ibb.co/3MJr1C0/6.jpg" alt=""/>

<br/>
<br/>

Download PHP and extract the zip file into the PHP directory you just created.
<br/>
<br/>


<img src="https://i.ibb.co/KW5yPDf/7.jpg" alt=""/>

<br/>
<br/>

Install Microsoft Visual C++
<br/>
<br/>


<img src="https://i.postimg.cc/W1qcKmZb/8.jpg" alt=""/>

<br/>
<br/>

Install MySQL
<br/>
<br/>


<img src="https://i.postimg.cc/QtXPXcF7/9.jpg" alt=""/>

<br/>
<br/>

Next we will have to create log in credentials. Be sure to store them somewhere because we will need the password later. 
<br/>
<br/>


<img src="https://i.postimg.cc/25xcX30S/10.jpg" alt=""/>

<br/>
<br/>

Open IIS as an Administrator 
<br/>
<br/>


<img src="https://i.postimg.cc/T3VCppMJ/11.jpg" alt=""/>

<br/>
<br/>

Navigate to PHP manager and selecet "Register new PHP version". There should be a "php-cgi.exe" file that appears. Select it!
<br/>
<br/>


<img src="https://i.ibb.co/s5MxXTg/12.jpg" alt=""/>
<img src="https://i.ibb.co/gwWx0ZX/13.jpg" alt=""/>


<br/>
<br/>

 Under IIS, Select the osTicket VM and select "Restart" under Manage Server
<br/>
<br/>


<img src="https://i.postimg.cc/k57w8q73/14.jpg" alt=""/>

<br/>
<br/>

Download osTicket and copy the upload file to wwwroot file in the inetpub file
<br/>
<br/>


<img src="https://i.postimg.cc/28vP7jNV/15.jpg" alt=""/>
<img src="https://i.postimg.cc/JnGFDMQ7/16.jpg" alt=""/>


<br/>
<br/>

Rename the file "osTicket"
<br/>
<br/>


<img src="https://i.ibb.co/Jt78dSP/17.jpg" alt=""/>

<br/>
<br/>

Return to IIS and restart the serve. Next select *80 (http) 
<br/>
<br/>


<img src="https://i.ibb.co/vQF7n7M/18.jpg" alt=""/>

<br/>
<br/>

This page will open. The red "X's" indicate the extensions that aren't enabled 
<br/>
<br/>


<img src="https://i.ibb.co/wRpmRgp/19.jpg" alt=""/>

<br/>
<br/>

Navigate over to IIS> Sites> Default Web Site> osTicket. Select PHP manager> Enable : php_imap.dll, php_intl.dll, php_opache.dll
<br/>
<br/>


<img src="https://i.ibb.co/W0tTgmw/20.jpg" alt=""/>

<br/>
<br/>

Afte enabling the PHP extenions. We can observe the changes. 
<br/>
<br/>

<img src="https://i.ibb.co/b7fVXzC/21.jpg" alt=""/>

<br/>
<br/>

Browse over to file explorer > C drive> osTicket> include> ostsampleconfig.php. Next we're going to remove the "sample" from the file name
<br/>
<br/>


<img src="https://i.ibb.co/G2thSYc/22.jpg" alt=""/>

<br/> 
<br/>

Right- click on ost-config.php> Properties> Security> Advanced> Disable Inheritance> Remove all inherited permissions from this object. Select the Add button to add permissions to the file> type "Everyone" > Check> OK> check all permissions> ok? apply> ok
<br/>
<br/>


<img src="https://i.ibb.co/S6KZX5Z/23.jpg" alt=""/>

<br/>
<br/>

Continue on the osTicket web page and fill out the set up page
<br/>
<br/>


<img src="https://i.ibb.co/BgGWgfn/24.jpg" alt=""/>

<br/>
<br/>

Install HeidiSQL
<br/>
<br/>


<img src="https://i.ibb.co/C0T7wkf/25.jpg" alt=""/>

<br/>
<br/>

After installation select New> Username> root> password> MySQL password we setup earlier in the MySQL setup> OPEN. Next on the left side, we will right-clik " unnamed" and create a new database named "osTicket". 
<br/>
<br/>

  
<img src="https://i.ibb.co/59yzcGC/26.jpg" alt=""/>
<img src="https://i.ibb.co/YP0xS0g/27.jpg" alt=""/>


<br/>
<br/>

Lastly, select Install and you should recieve a "Congratulations" from osTicket
<br/>
<br/>


<img src="https://i.ibb.co/zhVMSmf/28.jpg" alt=""/>
<img src="https://i.ibb.co/Rz805hL/29.jpg" alt=""/>



