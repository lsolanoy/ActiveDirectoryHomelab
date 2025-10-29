<img width="1114" height="498" alt="image" src="https://github.com/user-attachments/assets/3ff03300-600f-4c81-af40-49dce90950c8" />

<h1>Active Directory Homelab</h1>
Active Directory is Microsoft's centralized directory system used for managing users, systems and other resources within a network. It organizes these objects in a domain based structure where it can enforce authentiction, authorization and group policies.
<h2>Description</h2>
In this lab, we will create a virtualized Active Directory Homelab using VirtualBox. We will create two vritual machines, the first one being a Windows 11 host and the other will be a Windows Server 2022 host which will serve as the domain controller. We will place the VMs within the same VNET and join the Windows 11 host to the domain. The aim of this project is to guide individuals through the process of creating a basic Active Diretory Homelab where they can learn by simulating real-world scenarios.
<br />


<h2>Technologies Used</h2>

- <b>VirtualBox</b> 
- <b>Active Directory Domain Services</b>
- <b>Windows 11</b>
- <b>Windows Server 2022</b> 

<h2>Lab walk-through:</h2>
Windows 11 Host Setup

1. Download VirtualBox from this link:(https://www.virtualbox.org/wiki/Downloads). Choose the version that matches the OS of your host computer.
 <br/>
<img width="845" height="436" alt="Image" src="https://github.com/user-attachments/assets/e89f515b-e8cc-4539-9033-c133d581fd88" />
<br />
<br />
2. Now we will download the Windows 11 image from this link: (https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise)Select the "Windows 11 Enterprise" version. Fill out the form "Register for your free trial"  and download the ISO image for your specific language.
<br/>
<img width="838" height="428" alt="Image" src="https://github.com/user-attachments/assets/1e5ba2f7-5a36-4a7a-880a-e1c769e6d6e5" />
<br />
<br />
3. Open VirtualBox. On the main menu, click "New" and window will pop up.  Give the VM a name and select the Windows 11 ISO image we just downloaded. Lastly, check the box that says "Skip Unattended Installation". Click Next.
<br/>
<img width="887" height="534" alt="Image" src="https://github.com/user-attachments/assets/92a27c71-e89b-4416-a426-7e4bb7561ab4" />
<br />
<br />
4. The next page we will be choosing how much resources we want to allocate to the VM. For this specific VM we will be putting 4 GB and 2 Processors.
<br/>
<img width="881" height="505" alt="image" src="https://github.com/user-attachments/assets/26b6bace-58e8-4f6b-885e-f7c7922e900f" />
<br />
<br />
5. This page we select how large the virtual hard disk. We will leave this value at 80 GB.
<br/>
<img width="883" height="506" alt="image" src="https://github.com/user-attachments/assets/82e45ede-e9ca-4303-8faa-7ad5be3baea8" />
<br />
<br />
6. On the last page, it will show you the summary of your configurations and at this point you can click "Finish". On the main menu of VirtualBox you can boot up the VM by clicking "Start"
<br/>
<img width="867" height="442" alt="image" src="https://github.com/user-attachments/assets/eb2f4be0-3abd-43f9-8732-378fbe748b48" />=
<br />
<br />
7. Once the VM boots up you will have to go through the last bit of configurations: Select Your language, Select "Install Window 11", Accept License Terms, Select Disk you created to install, lastly click "Install".
<img width="765" height="582" alt="image" src="https://github.com/user-attachments/assets/93776ec1-d15b-4bc3-8bbc-84104e8135ed" />
<img width="748" height="577" alt="image" src="https://github.com/user-attachments/assets/53fb62c2-937a-4455-bf4f-d4c7595a7a68" />
<br />
<br />
8. The VM will restart again, and then you will have to go through the Windows Account Set-up: Select Region, Select Keyboard layout, Skip "Sign-in" Options, Enter name for device, Enter password, Choose privacy settings, then your finished. Login with your account and the host is ready for use.
<img width="1029" height="775" alt="image" src="https://github.com/user-attachments/assets/4d503f55-8384-46be-a2cd-dc1dcf34927a" />
<br />

Windows Server 2022 Setup
1. Download the Windows Server 2022 ISO image from this link: (https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022?msockid=0a7f04a9dbd163d10908128cda3f626a)
 <br/>
<img width="1886" height="934" alt="image" src="https://github.com/user-attachments/assets/84bdb97e-340c-4bca-8a24-2a67accb4cc5" />
<br />
<br />
2. On VirtualBox, click "New" and we will go the same process when we created the Windows 11 machine.
 <br/>
<img width="630" height="361" alt="image" src="https://github.com/user-attachments/assets/78673a3e-d916-43e5-9ef1-5714c4d0bcdc" />
<br />
<br />
3. For the hardware we will add 4096 MB and 2 cores. For thr virtual disk, we will put it to 50 GB. Once you hvae these configurations done, Click "Finish" and bootup VM.
 <br/>
<img width="638" height="366" alt="image" src="https://github.com/user-attachments/assets/2f78a62e-c8ff-4e7d-9d89-dbb85241d29d" />
<br />
<br />
4. Once the VM is up and running, we will have to go through the final setup: Select your language, Select "Desktop Experience" for OS, Select Custom Installation, then Install.
 <br/>
<img width="475" height="360" alt="image" src="https://github.com/user-attachments/assets/711f5ad3-9400-4e7b-899c-c349e589ceb1" />
<br />
<br />
5. The machine will restart and once it boots up again. We will have to create a password for the Administrator Account. Once the account is made you can login into the machine and it is ready for use.
 <br/>
<img width="746" height="554" alt="image" src="https://github.com/user-attachments/assets/67f2d236-415d-464a-807b-4195409ee9c0" />
<img width="774" height="586" alt="image" src="https://github.com/user-attachments/assets/bf55fb6c-4a25-42ed-838b-232afacfb911" />
<br />
<br />

Setting up Windows Server 2022 as Domain Controller
1. When we boot up the Windows Server VM the Server Manager Dashboard will open automactically. Here, we will turn this system into a DC.
<img width="1900" height="838" alt="image" src="https://github.com/user-attachments/assets/16c945d4-af31-45ea-9f64-8f01e66a75e1" />

</p>

