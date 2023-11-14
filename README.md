Active Directory

<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
The goal of this project is to deploy and configure your very own Active Directory home lab. This simplified tutorial will not only help you understand how Active Directory works but will also provide insight into how Windows networking works. 

<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b>
- <b>Oracle Vmware:</b> Deployed Window Server 2022 and Windows 10 ISO

<h2>Environments Used </h2>

- <b>Oracle VirtualBox</b>
- <b>Windows 10</b>
- <b>Server 2019</b>


<h2>Walk-through:</h2>

<p align="center">
Download and install Oracle VirtualBox, Windows 10 ISO, and Server 2019 ISO. Launch Oracle VirtualBox and create a virtual machine which will be our Domain Control.
: <br/>
<img src="https://i.imgur.com/UzaNKLX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Add an adapter for the internal network within the newly created Domain Control settings. The first adapter will have a Network Address Translation automatically assigned that connects to the house's internet. The second adapter will connect to the internal network:  <br/>
<img src="https://i.imgur.com/yRqFfbf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Run the Domain Control and install the server 2019 onto the VM when promoted: <br/>
<img src="https://i.imgur.com/Pmjzake.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set up the IP address for our internal network. There are two Ethernet options, one will route automatically to our home address the other we will configure in order to distinguish the two:  <br/>
<img src="https://i.imgur.com/iCfRhpc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Install Active Directory Domain Service to create a Domain on the appropriate server:  <br/>
<img src="https://i.imgur.com/5h9RuKC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<img src="https://i.imgur.com/I68JcnC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://i.imgur.com/6Sihr3V.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br />
<br />
Create our very own dedicated domain Admin account under the current domain instead of using the built-in Admin account. We can then create a new user/password within the domain and promote the user role as an Admin.:  <br/>
<img src="https://i.imgur.com/yGRCbPu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>
<img src="https://i.imgur.com/nPG6x7N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Logged in under the new admin account previously created and configured a remote server/network address translation (RAS/NAT) which will allow the client to be on the private virtual network and still be able to access the internet through the Domain Controller:  <br/>
<img src="https://i.imgur.com/H8NqOOF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://i.imgur.com/5QGUwQs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br />
<img src="https://i.imgur.com/NR6ztwZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />  
<br />
<img src="https://i.imgur.com/zxC8PXe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br />
<img src="https://i.imgur.com/koP1lfJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set up the Dynamic Host Configuration Protocol (DHCP) server on the Domain Controller. This will allow our Windows 10 client on the network to get an IP address that will allow them to browse:  <br/>
<img src="https://i.imgur.com/qSKxQz4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<img src="https://i.imgur.com/Y6DVwio.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 
<br/>
<img src="https://i.imgur.com/HqlnQQD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 
<br/>
<img src="https://i.imgur.com/o0YtMKr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 
<br/>
<img src="https://i.imgur.com/lUdz2Lg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
The Powershell script in this repository is responsible for making a new organization unit and adding users with a password that will be reset at login:  <br/>
<img src="https://i.imgur.com/PdHgnaq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 
<br/>
Create a new VM, and configure the setting to the internal network. Then launch Windows 10 on the VM:  <br/>
<img src="https://i.imgur.com/sDO5N78.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 
<br/>
<img src="https://i.imgur.com/6nJos7Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 
<br/>
Lastly, rename the Computer name to align with the CLient1 name and join the VM to the "Mydomain.com" domain:  <br/>
<img src="https://i.imgur.com/lYGFB4T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
