<h1>💻 Active Directory Home Lab</h1>

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

Change the name of your two adapters and make sure ones connected to internet and the other is internal 
<img src="https://i.imgur.com/b9BOVcc.jpeg" height="80%" width="80%" alt="NATn1"/>

Assign IP address to internal network X_INTERNET_X the second one.
<img src="https://i.imgur.com/nO241kQ.jpeg" height="80%" width="80%" alt="NATn2"/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
