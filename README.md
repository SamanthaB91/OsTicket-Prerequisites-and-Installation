<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Building the Cloud Backbone: Hands-on Active Directory Deployment in Azure</h1>
This project outlines the implementation of Active Directory within Azure Virtual Machines.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Before you start, you will need to have an active microsoft azure account.
- The first step will be setting up to create the virtual machines in microsoft azure. To do this you will need to create a resource group and a virtual network (VNET) To create the resource group, type resource group in the search engine and hit search. Then click on resource groups and click create. We will name the resource group, azure-test1. Click review and create. Once validated click create. Once completed we will then create our virtual network. We will do the same thing as we did to get to the resource groups, type virtual network in the search engine and click search. You will then click on virtual networks and click create. Make sure you have your subscription selected and in the section for resource groups make sure it has our newly created resource group, azure-test1. Our virtual network name will be, Azure-projectVnet. In the section for region put, (US) East US 2 (this will be the region we use for our virtual machines, so make sure to write it down somewhere). Click review and create. Once validated click create. After a minute or two both should be completed and we are now all set-up to create our vitual machines(VM's)  
- Our second step will be creating two virtual machines (VM's) You might be wondering why do we need two virtual machines. We need them in order to successfully install and deploy active dirctory. One virtual network will be our admin account and the other one will be a client account. We need both to successfully install and demonstrate we have deployed active directory correctly. Now we will create our first virtual machine by going to the search and type in virtual machines and click search. Click on virtual machines and click create. Make sure you have your subscription selected and in resource groups put our resource group, azure-test1. We will name our virtual machine, AD-1. Make sure the region is in (US) East US 2 (same as our virtual network). In the section for image we will use Windows server 2022 datacenter:azure edition. In the section for size, just make sure it has 2 vcpus. Our username will be, azureuser and our password, Cyberuser123. Next make sure you click the boxes in licensing. Click next until you get to networking. Make sure the virtual network is set to our created one, Azure-projectVnet. Then you can click review and create. Once it passes validation you can click create. While it's creating we can go ahead and create our second virtual machine. We are going to do the same process as the first one: go to virtual machines, click create, make sure your subscription is there, set resource group (azure-test1), the name this time will be cliet-1, the region is (US) East US 2, the image this time will be using Windows 11 pro (windows 10 pro is unavailable), the size will be the same as our first virtual machine,  our username will be: azureuser, the password: Cyberuser123!, remember to click the box for licensing and click next to networking to make sure our virtual network is Azure-projectVnet. Click review and create. Once validation is complete, click create. We now have our virtual machines created.
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="1901" height="1030" alt="image" src="https://github.com/user-attachments/assets/62ba3450-0c8d-470b-a28b-e5130d0363b8" />

</p>
<p>
This picture shows that our first step is completed in creating a resource group and a virtual network. Now we are all set to create our virtual machines.
</p>
<br />

<p>
<img width="1727" height="816" alt="image" src="https://github.com/user-attachments/assets/33de4a70-73e8-4214-b9f2-331fbef8f3a7" />

</p>
<p>
This photo shows we have our resource group, virtual network and our two vitual machines. We have our set-up complete. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
