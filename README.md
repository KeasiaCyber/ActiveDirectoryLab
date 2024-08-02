<h1>💻 Active Directory Home Lab 💾</h1>

<h2>Description</h2>
In this home lab project, I'll be walking you through the process of setting up an Active Directory environment using Oracle VirtualBox. We'll gain a deeper understanding of how Active Directory and Windows networking functions work. Let's dive in and explore how to set up this essential infrastructure together.
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

<h2> 1. Download and Install Oracle Virtual Box, Windows 10 and Server 2019: </h2>
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

<h2> 3. Install Server 2019 on the VM and assign IP address for the internal network: </h2>

Change the name of your two adapters and make sure one connected to the internet and the other is internal<br/>
<img src="https://i.imgur.com/b9BOVcc.jpeg" height="80%" width="80%" alt="NATn1"/>

Assign an IP address to internal network X_INTERNET_X the second one.<br/>
<img src="https://imgur.com/NzUH4eX.jpeg" height="80%" width="80%" alt="NATn2"/>
<br />
<br />


<h2> 4. Setup Domain / AD DS: </h2>
Install Active Directory Domain Services <br/>
<img src="https://imgur.com/Xc2bs0U.jpeg" height="80%" width="80%" alt="INSTALL AD DS"/>
<img src="https://imgur.com/MIm1sfO.jpeg" height="80%" width="80%" alt="INSTALL AD DS 2"/>

See the flag we now have to config a DC for our services by clicking that <br/>
<img src="https://imgur.com/P4jARVA.png" height="80%" width="80%" alt="Yellow Flag"/>

Add a new forest and create a password <br/>
<img src="https://imgur.com/8gYWj0k.png" height="80%" width="80%" alt="DC NAME SET"/>
<img src="https://imgur.com/WGXgpfW.png" height="80%" width="80%" alt="DC NAME SET"/>

Click Start and go to Active Directory User and Computers, Setup an organization unit for the Admin <br/>
<img src="https://imgur.com/HFnbwwf.png" height="80%" width="80%" alt="USER AND COMPUTERS 1"/>
<img src="https://imgur.com/8lABKY4.png" height="80%" width="80%" alt="USER AND COMPUTERS 2"/>
<img src="https://imgur.com/DZE1UBy.png" height="80%" width="80%" alt="USER AND COMPUTERS 3"/>

ADD users to the Admin sections that were created and make the user an admin<br/>
<img src="https://imgur.com/X2wVwsY.png" height="80%" width="80%" alt="USER AND COMPUTERS 4"/>
<img src="https://imgur.com/lgm2gYg.png" height="80%" width="80%" alt="USER AND COMPUTERS 5"/>

Right-click and go Properties then click on member of ADD, TYPE domain admins and check the name then click ok and apply. Restart the VM and sign in to the user you created<br/>
<img src="https://imgur.com/3Mi3WCG.png" height="80%" width="80%" alt="USER AND COMPUTERS 6"/>


<h2> 5. Configuring RAS / NAT: </h2>
Set up routing to enable clients on the private network to reach the internet via the domain controller.<br/>
<img src="https://imgur.com/xubaQBp.png" height="80%" width="80%" alt="RASNAT 1"/>
<img src="https://imgur.com/NpOFtwu.png" height="80%" width="80%" alt="RASNAT 2"/>
<img src="https://imgur.com/RO59b2Q.png" height="80%" width="80%" alt="RASNAT 3"/>
<img src="https://imgur.com/GahgXsm.png" height="80%" width="80%" alt="RASNAT 4"/>
<img src="https://imgur.com/NaB3pSP.png" height="80%" width="80%" alt="RASNAT 5"/>
<img src="https://imgur.com/lL5ttmZ.png" height="80%" width="80%" alt="RASNAT 6"/>
You may have to right click and authorize it and refresh it so the green arrow will appear <br/>
<img src="https://imgur.com/lp2qfqU.png" height="80%" width="80%" alt="RASNAT 7"/>


<h2> 6. Setup DHCP Scope for the domain controller(DC): </h2>
If we review the diagram above at begin we need to set the IP address from DHCP scope diagram<br/>
<img src="https://imgur.com/iKGlkJc.png" height="80%" width="80%" alt="DHCP 1"/>
<img src="https://imgur.com/gnQWn7H.png" height="80%" width="80%" alt="DHCP 2"/>
<img src="https://imgur.com/Q2wv5DP.png" height="80%" width="80%" alt="DHCP 3"/>
<img src="https://imgur.com/cW7RBsl.png" height="80%" width="80%" alt="DHCP 4"/>
<img src="https://imgur.com/Ka63s66.png" height="80%" width="80%" alt="DHCP 5"/>
<img src="https://imgur.com/BgAIW0e.png" height="80%" width="80%" alt="DHCP 6"/>
Make sure to add the IP address before clicking next, I made that mistake and couldn't figure out why the lab stopped working !<br/>
<img src="https://imgur.com/1seUF9L.png" height="80%" width="80%" alt="DHCP 7"/>
<img src="https://imgur.com/GwirEvM.png" height="80%" width="80%" alt="DHCP 8"/>
<img src="https://imgur.com/7ZQs2Vd.png" height="80%" width="80%" alt="DHCP 9"/>




<h2> 7. Create and run PowerShell Script ISE: </h2>
<img src="https://imgur.com/aTkgCsi.png" height="80%" width="80%" alt="PS 1"/>
<img src="https://imgur.com/VE6sbsN.png" height="80%" width="80%" alt="PS 2"/>



<h2> 7. Create another VM and install Windows 10: </h2>
 Make sure to go to settings for the VM and change the NAT to internal.<br/>
 <img src="https://imgur.com/rdgUfl8.png" height="80%" width="80%" alt="win 1"/>

 
Once  Windows 10 is installed it will be connected to the domain to check just ping in the cmd, now change the pc name, and we're done.<br/>
<img src="https://imgur.com/QEcqDKk.png" height="80%" width="80%" alt="win 2"/>
<img src="https://imgur.com/nfF0rbx.png" height="80%" width="80%" alt="win 3"/>



