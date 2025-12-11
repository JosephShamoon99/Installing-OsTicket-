<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>Installing OsTicket - Overview </h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. 

Since OsTicket is a web based application, in order to install OsTicket we will need 3 things: 

-A web server for users to access Ostciket 
-A database for tickets to be stored 
-The Osticket installion files themselves 

<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows 11</b> (21H2)

<h2>List of Prerequisites</h2>

<img width="1234" height="691" alt="install files" src="https://github.com/user-attachments/assets/0b77f96f-90e8-41d1-ad0a-77e11519c220" />

- OsTicket
- HediSQL
- mySQL
- PHP
- PHP Rewrite Module 
- Visual Code C++ Redistributable

<h2>Setting Up The Server</h2>

<p>
<img width="475" height="395" alt="enable GCI" src="https://github.com/user-attachments/assets/dd5c6012-4406-497b-a6d6-540989cc4df5" />
</p>
<p>
We will set up the server on our Windows vitural machine. You will need to enable IIS (Internet Information Services) to act as the server. Control Panel > Uninstall a program > Turn windows features on and off > Check ISS. 
</p>
<br />

<p>
<img width="407" height="817" alt="enable CGI 2 (2)" src="https://github.com/user-attachments/assets/4e5533cc-dbf8-4eef-96af-b2454cb65c7c" />
</p>
<p>
We will also need to enable CGI. ISS > World Wide Services > Application Development Features > Check CGI. 
</p>
<br />

<p> 
<img width="1118" height="508" alt="PHP folder" src="https://github.com/user-attachments/assets/ce18c29f-7dd0-4537-86e7-821c4af2bb6d" />
</p>
<p>
osTicket needs PHP to Work. 
We will need to create a PHP folder in your C drive and put the PHP installation files in there.
</p>
<br /> 

<p>
<img width="1234" height="691" alt="install files" src="https://github.com/user-attachments/assets/0b77f96f-90e8-41d1-ad0a-77e11519c220" />
</p>
<p>
Once we have PHP installed we will need to install the PHP manger for IIS and along with the rewrite module. 
You will also need to install a visual code c++ redistributable.
</p>
<br /> 

<p>
<img width="1420" height="739" alt="IIS ad admin" src="https://github.com/user-attachments/assets/842f118e-ebb4-4de0-b45c-998fd12fc8e7" /> 
<img width="1421" height="741" alt="PHP manager" src="https://github.com/user-attachments/assets/8a23e2c7-1117-43bd-8434-d9da2772cc7f" />
<img width="940" height="528" alt="PHP exe selected" src="https://github.com/user-attachments/assets/820391ff-c1be-47d1-be40-5e3d42d3322e" />
</p>
<p>
We will need to make IIS aware of the version we have of PHP. We can do this by opening IIS as an admin > PHP manger > register PHP > enter path to PHP executable. 
</p>
<br />  

<h2>Setting Up The Database</h2> 

<p>
For the database you will need to install SQL and create a username and password for you the database. 
</p>
<br /> 

<p>
<img width="934" height="592" alt="HediSQL" src="https://github.com/user-attachments/assets/849fed57-aca2-4662-ae24-bd8197694915" />
</p>
<p>
You will also need to install HediSQL to interact with the database. Once HediSQL is installed, create a new table callled OsTciket. This is where our tickets will be stored.
</p>
<br /> 

<h2>Installing OsTicket</h2> 

<p>
<img width="1122" height="546" alt="osTciket in root" src="https://github.com/user-attachments/assets/74f1cd9b-4567-44f8-a6d2-f6b027cc5bc5" />
</p>
<p>
We can now install the osTicket files.  

There should be 2 folders inside the osTicket folder: 

-scripts  
-uploads

Change the name of the upload folder to osTicket.

We will need to place the osTicket in the wwwroot folder.  

C:\ > inetpub > wwwroot 
</p>
<br />  

<p>
<img width="1123" height="899" alt="rename ost-config" src="https://github.com/user-attachments/assets/ffc07ff7-ddb8-430e-97ab-7bcc255c48c4" /> 
<img width="766" height="513" alt="disable inhertience " src="https://github.com/user-attachments/assets/1135ef36-cf2d-4cbf-a2d0-7d4a46ebbfe6" /> 
<img width="361" height="451" alt="new permsiions for everyone" src="https://github.com/user-attachments/assets/363aae37-9a84-4a4b-868c-7800979dee8c" />
</p>
<p>
We will need to change the name of the OS configuration file to ost-config.php and we will need to change the permissions on the file for IIS to access it. 
</p>
<br />  

<p>
<img width="1417" height="744" alt="port 80" src="https://github.com/user-attachments/assets/f09ff34a-8d65-4615-b44a-cc1fab99453b" /> 
</p>
<p>
We can now see the OsTicket folder inside the ISS dashboard. 

We can open OsTicket in the web browser on port 80.
</p>
<br />   

<p>
<img width="926" height="839" alt="unabled php extenstions " src="https://github.com/user-attachments/assets/ef5d5647-9ff7-49e8-b346-9e1d681fe834" />
<img width="1422" height="739" alt="enabled extensions " src="https://github.com/user-attachments/assets/88b9e817-a5fe-4a6e-ac93-fda0ae939943" /> 
  </p>
<p>
Some PHP extensions are disabled and others are enabled. We can go to the OsTicket folder from the ISS dashboard and edit PHP extensions. 
</p>
<br />   

<p>
<img width="928" height="845" alt="connection database to osTicket" src="https://github.com/user-attachments/assets/7dff3cd3-aa1d-42d2-81fa-8323f1c83b66" />
</p>
<p>
WE can now connect OsTciket to our database we cretaed earlier using the username and passowrd for our database and selecting the OsTicket table we made in HediSQl.
</p>
<br />   

<p>
<img width="921" height="848" alt="finshed project" src="https://github.com/user-attachments/assets/2e116209-8a7d-45ba-9f7b-ea4ac4e6e220" />
</p>
<p>
OsTicket is now installed on our windows virtual machine 
</p>
<br />  




