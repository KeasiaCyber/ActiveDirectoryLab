<h1>💻 Active Directory Home Lab 💾</h1>

<h2>Description</h2>
In this home lab project, I'll be walking you through the process of setting up an Active Directory environment using Oracle VirtualBox. By following this tutorial by Josh Madakor (https://www.youtube.com/@JoshMadakor), we'll gain a deeper understanding of how Active Directory and Windows networking function works. Let's dive in and explore together how to set up this essential infrastructure.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Orcale Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>

<h2>Program walk-through:</h2>

<p align="center">

<h2>Diagram: </h2>
<img src="https://imgur.com/oNyNXTX.png" height="80%" width="80%" alt="Diagram"/>

<h2> 1. Download and Install Orcale Virtual Box, Windows 10 and Sever 2019: </h2>
Orcale Virtual Box: https://www.virtualbox.org/wiki/Downloads <br/>
Sever 2019: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019 <br/>
Windows 10: https://www.microsoft.com/en-us/software-download/windows10 <br/>


<h2> 2. Setup the Virtual Machine and Add two Network Adapters: </h2>

Create a new virtual machine by clicking on "New" in VirtualBox, naming it "Domain Controller(DC)", and selecting the "Windows Server 2019" ISO file as the boot media.<br/>

<img src="https://imgur.com/4wSNCOz.png" height="80%" width="80%" alt="DC"/>

<img src="https://imgur.com/fRIsaDs.png" height="80%" width="80%" alt="Hardware"/>

<img src="https://imgur.com/DTSerxo.png" height="80%" width="80%" alt="Size"/>

Configure the virtual machine by giving it two network adapters: one for connecting to the internet and the other for the private network.<br/>

<img src="https://imgur.com/XYT79Hj.png" height="80%" width="80%" alt="NET1"/>

<img src="https://imgur.com/veRrLQW.png" height="80%" width="80%" alt="NET2"/>

<h2> 3. Install Server 2019 on the VM and assign IP addressing for the internal network: </h2>

Change the name of your two adapters and make sure ones connected to internet and the other is internal<br/>
<img src="https://i.imgur.com/b9BOVcc.jpeg" height="80%" width="80%" alt="NATn1"/>

Assign IP address to internal network X_INTERNET_X the second one.<br/>
<img src="https://imgur.com/NzUH4eX.jpeg" height="80%" width="80%" alt="NATn2"/>
<br />
<br />


<h2> 4. Setup Domain / AD DS : </h2>
Install Active Directory Domain Services <br/>
<img src="https://imgur.com/Xc2bs0U.jpeg" height="80%" width="80%" alt="INSTALL AD DS"/>
<img src="https://imgur.com/MIm1sfO.jpeg" height="80%" width="80%" alt="INSTALL AD DS 2"/>

See the flag we now have to config a DC for our services by clicking that <br/>
<img src="https://imgur.com/P4jARVA.png" height="80%" width="80%" alt="Yellow Flag"/>

Add a new forest and create a password <br/>
<img src="https://imgur.com/8gYWj0k.png" height="80%" width="80%" alt="DC NAME SET"/>
<img src="https://imgur.com/WGXgpfW.png" height="80%" width="80%" alt="DC NAME SET"/>

Click Start and go to Active Directory User and Computers, Setup an organzation unit for the Admin <br/>
<img src="https://imgur.com/HFnbwwf.png" height="80%" width="80%" alt="USER AND COMPUTERS 1"/>
<img src="https://imgur.com/8lABKY4.png" height="80%" width="80%" alt="USER AND COMPUTERS 2"/>
<img src="https://imgur.com/DZE1UBy.png" height="80%" width="80%" alt="USER AND COMPUTERS 3"/>

ADD users to the Admin sections that was created and make the user a admin<br/>
<img src="https://imgur.com/X2wVwsY.png" height="80%" width="80%" alt="USER AND COMPUTERS 4"/>
<img src="https://imgur.com/lgm2gYg.png" height="80%" width="80%" alt="USER AND COMPUTERS 5"/>

Right click and go Properties then click on member of ADD, TYPE domain admins and check the name then click ok and apply. Restart VM and sign in to the user you created<br/>
<img src="https://imgur.com/3Mi3WCG.png" height="80%" width="80%" alt="USER AND COMPUTERS 6"/>


<h2> 5. Configuring RAS / NAT: </h2>
Set up routing to enable clients on the private network to reach the internet via the domain controller.<br/>
<img src="https://imgur.com/xubaQBp.png" height="80%" width="80%" alt="RASNAT 1"/>
<img src="https://imgur.com/NpOFtwu.png" height="80%" width="80%" alt="RASNAT 2"/>
<img src="https://imgur.com/lL5ttmZ.png" height="80%" width="80%" alt="RASNAT 3"/>
<img src="https://imgur.com/lp2qfqU.png" height="80%" width="80%" alt="RASNAT 4"/>


<h2> 6. Setup DHCP Scope for the domain controller(DC): </h2>
<br/>
<img src="https://imgur.com/RexGA3K.png" height="80%" width="80%" alt="DHCP 1"/>
<img src="https://imgur.com/Mtgf5Ci.png" height="80%" width="80%" alt="DHCP 2"/>
<img src="https://imgur.com/lL5ttmZ.png" height="80%" width="80%" alt="DHCP 3"/>


Download and run Power Script<br/>
<img src="https://imgur.com/aTkgCsi.png" height="80%" width="80%" alt="PS 1"/>
<img src="https://imgur.com/VE6sbsN.png" height="80%" width="80%" alt="PS 2"/>



<h2> 7. Create another VM and install Windows 10: </h2>
<br/>
<img src=".png" height="80%" width="80%" alt="win 1"/>


