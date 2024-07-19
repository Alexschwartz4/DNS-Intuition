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

- Step 1: Setup Resources in Azure
<p>

</p>
<p>
Create the Domain Controller VM (Windows Server 2022) named “DC-1”
 </p>
<img src="https://imgur.com/AfsY0Rp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
Set Domain Controller’s NIC Private IP address to be static
 </p>
 <img src="https://imgur.com/dkd3YDU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
Create the Client VM (Windows 10) named “Client-1”. Use the same Resource Group and Vnet of DC-1
 </p>
  <img src="https://imgur.com/QJptNyi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  </p>
<br />
- Step 2: Ensure Connectivity between the client and Domain Controller
</p>
<p>
