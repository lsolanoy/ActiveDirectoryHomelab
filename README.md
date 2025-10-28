<h1>Active Directory Homelab</h1>
Active Directory is Microsoft's centralized directory system used for managing users, systems and other resources within a network. It organizes these objects in a domain based structure where it can enforce authentiction, authorization and group policies.
<h2>Description</h2>
In this lab, we will create a virtualized Active Directory Homelab using VirtualBox. We will create two vritual machines, the first one being a Windows 11 host and the other will be a Windows Server 2022 host which will serve as the domain controller. We will place the VMs within the same VNET and join the Windows 11 host to the domain.
<br />


<h2>Technologies Used</h2>

- <b>VirtualBox</b> 
- <b>Active Directory Domain Services</b>
- <b>Windows 11</b>
- <b>Windows Server 2022</b> 

<h2>Lab walk-through:</h2>

 <br/>
	1. Download VirtualBox from this link:(https://www.virtualbox.org/wiki/Downloads). Choose the version that matches the OS of your host computer.
 <br/>
<img src=(https://imgur.com/a/8C1vLkU)>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
