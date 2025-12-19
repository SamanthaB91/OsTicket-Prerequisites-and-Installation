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
- Our second step will be creating two virtual machines (VM's) You might be wondering why do we need two virtual machines. We need them in order to successfully install and deploy active dirctory. One virtual machine will be our domain controller (AD-1) and the other one will be a client account (Client-1). Now we will create our first virtual machine by going to the search and type in virtual machines and click search. Click on virtual machines and click create. Make sure you have your subscription selected and in resource groups put our resource group, azure-test1. We will name our virtual machine, AD-1. Make sure the region is in (US) East US 2 (same as our virtual network). In the section for image we will use Windows server 2022 datacenter:azure edition. In the section for size, just make sure it has 2 vcpus. Our username will be, azureuser and our password, Cyberuser123. Next make sure you click the boxes in licensing. Click next until you get to networking. Make sure the virtual network is set to our created one, Azure-projectVnet. Then you can click review and create. Once it passes validation you can click create. While it's creating we can go ahead and create our second virtual machine. We are going to do the same process as the first one: go to virtual machines, click create, make sure your subscription is there, set resource group (azure-test1), the name this time will be cliet-1, the region is (US) East US 2, the image this time will be using Windows 11 pro (windows 10 pro is unavailable), the size will be the same as our first virtual machine,  our username will be: azureuser, the password: Cyberuser123!, remember to click the box for licensing and click next to networking to make sure our virtual network is Azure-projectVnet. Click review and create. Once validation is complete, click create. We now have our virtual machines created. Now before we move on to the next step there is something very important we must do first and that is setting our domain controller's (AD-1) nic private IP address to be static. We need it to be static (meaning it won't change) since it is a server and will be our DNS server as well. We will be manually configuring our Client-1 VM to use our domain controller as a DNS server and if the private IP address changes then the settings we just configured won't be valid. To set our domain controller's VM (AD-1) private ip address to static we first go to virtual machines, click AD-1, then you will click networking and then click network settings. Next we will click ad-1216_z1(primary)/ipconfig(primary) which will bring us to the ip settings. We will then click ipconfig1 which will bring up a screen on the side. Under private ip address settings change from dynamic to static then click save.   
- In step three we will log into our vitual machines. First we will log into our domain controllers VM (AD-1) to first disable the firewall (only do in a practice setting) that way when we go into Client-1's VM and open powershell to try pinging AD-1's private ip address we won't get an error. To log into AD-1's VM, click the windows icon at the bottom of your screen and type remote desktop. Next go back to azure and click virtual machines. Then click AD-1 and look for the public ip address and copy it. Next paste it in the remote desktop space for computer and click connect. Once the enter credentials screen pops up click more choices, click use a different account and enter in AD-1's username and password. Click ok and wait for the VM to load. Once eveeything is loaded then right click the windows button and click run. Then you will type wf.msc and click ok. This will bring up windows firewall. To diable it click windows defender firewall properties and click off in the firewall state in the tabs domain profile, private profile and public profile. Then click apply and ok. The firewall for our doamin controller account is now off. Next we will configure Client-1's DNS settings to Ad-1's private ip address. We will minimize remote desktop and go back to microsoft azure. Go to virtual machines and click AD-1. Look for AD-1's private ip address and copy it. Next we will go to Client-1 in virtual machines. CLick network settings and click on ad-1216_z1(primary)/ipconfig(primary). On the left click DNS servers below ip configurations and then click custom. Here we will paste AD-1's private ip address and then click save. Next we will restart Client-1's VM to make sure the settings reset to the changes we jsut made. To do this go back to virtual machines, click the box for Client-1 and click restart. Once its done restarting we will log into Client-1's VM like we did with AD-1. Once the VM loads set the privacy settings to no and click accept. Now we will attempt to ping AD-1's private ip address. Minimize the remote desktop, go to virtual machines, click AD-1, copy the private ip address and go back into Client-1. Next we will open powershell by clicking the windows button and type powershell into search then click on it to open. In powershell type ping (AD-1's private ip address) and hiot enter. If done correctly you will see reply from (AD-1's private ip address). Now we will type ipconfig /all to make sure AD-1's private ip address is in the DNS settings. 
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
<img width="1897" height="1028" alt="image" src="https://github.com/user-attachments/assets/bbf55888-9431-4bde-9855-d422b3490699" />

</p>
<p>
This photo shows us changing the private ip address settings from dynamic to static.
</p>
<br />


<p>
  <img width="1255" height="862" alt="image" src="https://github.com/user-attachments/assets/3b6b6cbb-471e-4d3c-9a46-d5b2a24165a9" />

</p>

<p>
 This photo shows what the remote desktop looks like and the login screen for our domain controller's VM. 
</p>
<br />

<p>
 <img width="1620" height="928" alt="image" src="https://github.com/user-attachments/assets/bea0e278-0267-447b-8cfe-689721f26385" />
 
</p>

<p>
This photo shows powershell open in Client-1's VM and us about to attempt pinging AD-1's private ip address.
</p>
<br />

<p>
  <img width="1584" height="877" alt="image" src="https://github.com/user-attachments/assets/9a1f1447-a99e-44e4-aea8-35fa9d4a5375" />

</p>

<p>
  This photo shows the DNS servers in ipconfig /all are set to AD-1's private ip address.
</p>
<br />

<p>
  
</p>

<p>
  
</p>
<br />
