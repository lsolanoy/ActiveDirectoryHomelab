<img width="1114" height="498" alt="image" src="https://github.com/user-attachments/assets/3ff03300-600f-4c81-af40-49dce90950c8" />

<h1>Active Directory Homelab</h1>
Active Directory is Microsoft's centralized directory system used for managing users, systems and other resources within a network. It organizes these objects in a domain based structure where it can enforce authentication, authorization and group policies.
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
6. On the last page, it will show you the summary of your configurations and at this point you can click "Finish". On the main menu of VirtualBox you can boot up the VM by clicking "Start".
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
1. When we boot up the Windows Server VM the Server Manager Dashboard will open automatically. Here, we will turn this system into a DC.
 <br/>
<img width="1900" height="838" alt="image" src="https://github.com/user-attachments/assets/16c945d4-af31-45ea-9f64-8f01e66a75e1" />
<br />
<br />
2. First we will change name of computer by going to the search bar and typing "View your PC name" > Rename this PC > Name it "DC01" > Restart Machine. The purpose of this is to give the computer an easy naming convention to follow.
<br/>
<img width="1034" height="520" alt="image" src="https://github.com/user-attachments/assets/db9b2b2b-d898-4ebc-982f-48d061383e20" />
<br />
<br />
3. Now we will be configuring this machine as the domain controller. On the main menu of sever manager click "Manage" > click "Add Roles and Features"
<br/>
<img width="842" height="602" alt="image" src="https://github.com/user-attachments/assets/34482f94-b49f-4f73-8e0f-7670098c02b8" />
<br />
<br />
4. Now we will go through the options to select for each section. Click "Next" > Select "Role-based or feature based installation" > Select "DC01" in Server Pool > Check the box next to "Active Directory Domain Services" > Click "Next" > Click Install.
 <br/>
<img width="837" height="601" alt="image" src="https://github.com/user-attachments/assets/e647cc6a-cfc5-4935-8584-371a43697f9f" />
<br />
<br />
5. Once the installion is completed click on the option "Promote this server to a domain controller".
<br/>
<img width="832" height="593" alt="image" src="https://github.com/user-attachments/assets/f574415d-e576-4af4-81e2-91ee6f593edd" />
<br />
<br />
6. These will be the selections for Configuring Active Directory: Select "Add a new forest", Name your domain with ".local" at the end of it > Create password > Click "Next" > Click "Next" > Make sure all configurations are correct then click "Next" > The system will go through a prerequisite check > Once all checks are passed you can begin installation.
<br/>
<img width="805" height="594" alt="image" src="https://github.com/user-attachments/assets/d44b9871-9ebb-4218-af9a-b2d65355db99" />
<img width="821" height="600" alt="image" src="https://github.com/user-attachments/assets/24b047e0-a156-46df-b56c-387d6f97cde6" />
<br />
<br />
7. This VM is now configured as the Domain Controller. You can confirm by navgating to Active Directory Users and Computers and click on the Domain Controllers Tab.
<br/>
<img width="750" height="531" alt="image" src="https://github.com/user-attachments/assets/8e13ecea-c34c-4188-a9c8-89701e398f88" />
<br />
<br />

Creating Domain Users
1. We will create users in this domain that will be able to login from the Windows 11 host. First, on your Domain Controller open the Server Mangeer. Go to "Tools" > Active Directory Users and Computers.
<br/>
<img width="604" height="427" alt="image" src="https://github.com/user-attachments/assets/bfede819-1248-4e2e-9647-b4d6c2a3e777" />
<br />
<br />
2. Click on the Users folder. Right click anywhere on the white space under the users and Select New. A window will pop up where you can create a new user.
<br/>
<img width="355" height="297" alt="image" src="https://github.com/user-attachments/assets/c95971e6-1641-496a-a119-4e81c01d6d5f" /> <img width="355" height="297" alt="image" src="https://github.com/user-attachments/assets/4c299920-1848-4213-9a91-bbe7a4c144cf" />
<img width="355" height="297" alt="image" src="https://github.com/user-attachments/assets/523cf91a-7d42-46aa-929f-cf63c5b782b6" />

<br />
<br />
3. Use any name that you want. For the logon name use the first letter of the first name followed by the last name. Click "Next". Set a password for user and check the box that says password never expires. However, in a real work environment it would be set to "user must change password at next logon" for best security practice. Click "Finish" and user has been successfully created. Create 2 additional users.
<br/>
<br/>
Join Windows 11 VM to Domain
1. First we have to create a NAT Network where the VMs will reside in. On th main menu of VirtualBox go to File > Tools > Network Manager. On this page click on the "NAT network" tab and click "Create". Give the network a name. Click Apply.
<br/>
<img width="755" height="639" alt="image" src="https://github.com/user-attachments/assets/6dbf8441-0ec5-4928-92df-dcbf91715d0a" />
<br />
<br />

2. Now we will have to attach the VMs to the Network. On main menu of VirtualBox click on your Windows 11 VM > click "Settings > Select "Network" tab. Next to the "Attached To:" option, select NAT Network. For the "name" option select the network you created. Repeat these steps for the other VM.
<br/>
<img width="1029" height="810" alt="image" src="https://github.com/user-attachments/assets/7e147948-6fd9-4061-8eee-fecaa0574f01" />
<br />
<br />

3. Make sure both VMs are running. Log into your DC. First, we will set the server to have a static IP address. Go to command prompt and type "ipconfig", take note of the IP address. Now we will set static IP by searching Settings > Change Adpater Options > Right-click on the adapter for domain > Click Properties > Click IPv4 > Click Use the folllwing IP address. Copy the same IP address, Subnet Mask and Default Gateway from "ipconfig" output. For DNS server set it to 127.0.0.1 because this machine will host DNS.
<br/>
<img width="690" height="507" alt="image" src="https://github.com/user-attachments/assets/4cce55ae-88e5-4a0c-a563-c3f3992c7a65" />
<img width="1002" height="543" alt="image" src="https://github.com/user-attachments/assets/de27b294-2f67-45bc-8ffb-f1d07b5d5170" />
<br />
<br />

4. Now we will login to the Windows 11 VM. First we will chnage the computer's name. Search "view your PC name" > Click "Rename this PC" > Name it "WS01". This makes it easier to indentify this PC.
<br/>
<img width="565" height="229" alt="image" src="https://github.com/user-attachments/assets/0963bc03-cdcf-4530-9822-0a127e84e17b" />
<br />
<br />

5. We will also set a static IP address for this machine. Go to command prompt and type "ipconfig" command. Take note of output. Navigate to the adapter settings shown in previous steps and fill out the IPv4 properties. For the DNS server addresss we will set it to the IP of the server.
<br/>
<img width="356" height="403" alt="image" src="https://github.com/user-attachments/assets/319c533b-bee7-4a92-a9cd-b0f98a9af197" />
<br />
<br />

6. Finally, we will be attaching the Windows 11 Machine to the domain. Search "access work or schools" > Click "connect" > Click "Join this device to local Active Directory domain" > Enter Domain name > Enter username and password of domain admin > VM will restart. Once your VM restarts you will see that you can login into domain as administrator or we can login as the other users we made previously.
<br/>
<img width="588" height="577" alt="image" src="https://github.com/user-attachments/assets/cbbfc0fe-2ae9-421f-8ed6-ca6c28b9036d" />
<img width="593" height="245" alt="image" src="https://github.com/user-attachments/assets/582674fe-2a99-47d5-8bff-444ea2be8ff6" />
<img width="946" height="707" alt="image" src="https://github.com/user-attachments/assets/a6bd0eda-c076-4fa3-95c9-6470e885d0d4" />
<br />
<br />
</p>

