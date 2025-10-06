<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Preparing Virtual Setup in Azure
- Deploying Active Directory
- Creating Users via PowerShell
- Exploring Group Policy and Managing Accounts

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>Preparing Virtual Setup in Azure </h3>
<p>
  In this step, I setup the foundational environment in Microsoft Azure to prepare for deploying Active Directory services.</p>
   <p>Two seperate virtual machines are created inside the same virtual network and subnet: 
<ul>
  <li>DC-1: Windows Server (Domain Controller .</li>
  <li>Client-1: Windows 10 (used to connect to the domain)</li> 
</ul>
 <h4>DC-1 Configuration</h4>
   <ul> 
     <li>Set the network interface card private IP address to static to prevent changing IP</li>
     <li>log in via Remote Desktop</li>
     <li> Disable Windows Firewall to be able to test connectivity</li>
   </ul>
 <h4>Client-1 Configuration</h4>
   <ul>
     <li>Set the DNS server to DC-1's private IP address</li>
     <li>Restart the VM from the Azure Portal to apply changes</li>
     <li>Log in via Remote Desktop and ping DC-1's private IP to confirm network connectivity</li>
     <li>In PowerShell run ipconfig /all to verify that the DNS setting corretly point to DC-1's IP address</li>
   </ul>
<h4><i>What We Achieved</i></h4>
This setup establishes the network foundation required for Active Directory deployment. By ensuring the connectivity between the client and the domain controller, we confrim that:
<ul>
    <li>DNS resolution is correctly configured</li>
    <li>Internal routing between VMs functions as expected</li>
</ul>
This step validates Azure network configuration before installing and promoting DC-1 as the domain controller.
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />
