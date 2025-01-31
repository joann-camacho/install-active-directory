
<h1> Set up Active Directory Domain Services on the Domain </h1>
In this tutorial, we will guide you through the process of installing Active Directory Domain Services on a Windows Server operating system.  <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2) ***(Client-1)***
- Windows Server 2022 Datacenter Azure Edition ***(Domain Controller/ DC-1)***

<h2>High-Level Steps</h2>

 ***A- Prereq: Create a Windows VM and Windows Server VM in Azure. Then, remote login to Windows Server VM (DC-1). Select the link to learn how to [create VM in Azure](https://github.com/joann-camacho/create-windows-virtual-machine)*** 
  
- Step 1: Remote into DC-1 VM and install Active Directory Domain Services (ADDS).
- Step 2: Post configuration of Active Directory Domain Services.
- Step 3: Restart and then log back into DC-1 as user: mydomain.com\labuser

<h2>Actions and Observations</h2>

<p>
Step 1: Remote into Dc-1. Select the windows icon located at the bottom left corner. Select the Server Manager option. Select 'Add roles and features' option.
  
    Follow the props: In the Before You Begin, select 'Next. 
    In the Installation Type, Select 'Next'.
    In the Server Selection, make sure the DC-1 is highlighted and select, 'Next'.
    In the Server Roles, Click to select 'Active Directory Domain Services' and select 'Add features'. Select 'Next.
    In Features, Select 'Next'.
    In AD DS, Select 'Next'.
    In Confirmation, Click the box to "Restart the destination server automatically if required".
    Select 'Ok' in the disclaimer box. Select 'Install'.
        
</p>
<p>
  
![image](https://github.com/user-attachments/assets/c657a706-97ee-45cd-8c6c-1a74aa1614c3)
</p>

       After AD DS is installed. Select 'Close.
<br />

<p>
Step 2: Select the flagged disclaimer seen at the top right-hand side of Service Manager. We will begin the process of Post configurations:
  
     Deployment Configurations, Select 'add a new forest', name the root domain: mydomain.com. Select 'Next'.
     Domain Control Operations, type in a password and confirm it, then select 'Next'.
     DNS server- box must be unchecked.
     Additonal Options, Select 'Next'.
     Paths, select 'Next'.
     Review Options, select 'Next'.
     Prerequisites Check, and select 'Install'.
  
     Wait for the forest to be installed and created in the domain. The computer will restart and you will need to log in
     using your new credentials: username: mydoamin.com\labuser1  / password: (password created when creating the VM in Azure)     
</p>
<p>
  
![image](https://github.com/user-attachments/assets/37b54eed-838f-4810-bbce-55e0c8b607ae)
</p>

![image](https://github.com/user-attachments/assets/a38da77a-c405-4411-bd20-55aabd144351)








---------------------...........
<br />

<p>
Step 3: Right-click the windows icon located on the bottom left. Select the 'Systems' option. Select the 'Rename this PC (advanced)' option. 
        In the Systems Properties box, select 'Change' to rename this computer or domain. In Computer Name/Domain Changes box, click 'Domain' and type: 'mydomain.com'. Select
</p>
<p>
  
![image](https://github.com/user-attachments/assets/48c4ac0c-e8e7-4700-9d74-514f81273b2a)
</p>

(After installing Wireshark licensing terms) Open Wireshark. Double-click on 'Ethernet' to view IP traffic. This traffic is the IP packets reciprocating in the background while using the computer. 
<p>
  
![image](https://github.com/user-attachments/assets/8a7ba9ea-4008-4fce-9bd1-5a96153ddd3c)  
</p>
<br />

<p>
Step 3: Obtain Ubuntu (linux) Private IP address from Azure. In Wireshark's search window, Type ICMP. Also, open Powershell and ping 10.1.0.5 (Ubuntu's Private IP address). Observe the connectivity between two separate operating systems, when inspecting this traffic notice the four requests and replies in the Powershell command and there are 8 requests and replies in the Wireshark analyzer. This is important to note when inspecting data packet units and sourcing their incoming and outgoing traffic.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/6c90b2b5-70a6-4033-9307-de5dcaffcd57)
</p>
<br />

<p>
Step 4: In Wireshark, expand 'Ethernet II,Src' (Level 2 of the OSI model), and notice the MAC address given by Azure software. In Powershell type: 'ipconfig /all' to verify Windows VM MAC address are the same. This is important to analyze the source and destination MAC address it belongs to, which in this case Windows is the source.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/e2fee6ee-7a54-4b28-ab0e-cfce5d2f8471)
  
</p>
<br />

