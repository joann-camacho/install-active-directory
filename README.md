
<h1> Set up Active Directory Domain Services on the Domain </h1>
In this tutorial, we install Active Directory Domain Services on the Windows server operating system.  <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2) ***(Client-1)***
- Windows Server 2022 Datacenter Azure Edition ***(Domain Controller)***

<h2>High-Level Steps</h2>

 ***A- Prereq: Create a Windows VM and Windows Server VM in Azure. Then, remote login to Windows Server VM. Select link to [create VM in Azure](http://portal.azure.com)*** 
  
- Step 1: Install [Wireshark](https://www.wireshark.org) in the Windows VM to observe Packet tracing.
- Step 2: Attempt to ping Linux VM in Windows VM using Powershell. Observe the traffic in Wireshark
- Step 3: Verify the Windows VM MAC Address is the same.

<h2>Actions and Observations</h2>

<p>
Step 1: In the Windows VM, use the search engine, and visit [Wireshark](https://www.wireshark.org). Go to Downloads, and install Windows x64 Installer.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/f004b1cf-c6b4-45ab-8775-9b223a2d65e0)
</p>

(After installing Wireshark licensing terms) Open Wireshark. Double-click on 'Ethernet' to view IP traffic. This traffic is the IP packets reciprocating in the background while using the computer. 
<p>
  
![image](https://github.com/user-attachments/assets/8a7ba9ea-4008-4fce-9bd1-5a96153ddd3c)  
</p>
<br />

<p>
Step 2: Obtain Ubuntu (linux) Private IP address from Azure. In Wireshark's search window, Type ICMP. Also, open Powershell and ping 10.1.0.5 (Ubuntu's Private IP address). Observe the connectivity between two separate operating systems, when inspecting this traffic notice the four requests and replies in the Powershell command and there are 8 requests and replies in the Wireshark analyzer. This is important to note when inspecting data packet units and sourcing their incoming and outgoing traffic.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/6c90b2b5-70a6-4033-9307-de5dcaffcd57)
</p>
<br />

<p>
Step 3: In Wireshark, expand 'Ethernet II,Src' (Level 2 of the OSI model), and notice the MAC address given by Azure software. In Powershell type: 'ipconfig /all' to verify Windows VM MAC address are the same. This is important to analyze the source and destination MAC address it belongs to, which in this case Windows is the source.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/e2fee6ee-7a54-4b28-ab0e-cfce5d2f8471)
  
</p>
<br />

