
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
Step 2: Select the flagged disclaimer seen at the top right-hand side of Service Manager. 
  
<p>
  
![image](https://github.com/user-attachments/assets/37b54eed-838f-4810-bbce-55e0c8b607ae)
</p>
  
  
  We will begin the process of Post configurations:
  
     Deployment Configurations, Select 'add a new forest', name the root domain: mydomain.com. Select 'Next'.
     Domain Control Operations, type in a password and confirm it, then select 'Next'.
     DNS server- box must be unchecked.
     Additonal Options, Select 'Next'.
     Paths, select 'Next'.
     Review Options, select 'Next'.
     Prerequisites Check, and select 'Install'.
  
     Wait for the forest to be installed and created in the domain. The computer will restart and you will need to log in
     using your new credentials: username: mydoamin.com\labuser1  / password: (password created when creating the VM in Azure)     

<p>
  
 ![image](https://github.com/user-attachments/assets/a38da77a-c405-4411-bd20-55aabd144351)
 
</p>


<br />
