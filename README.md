<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory DNS Excersise</h1>
This tutorial demonstrates the intuition of on-premises Active Directory DNS use within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell
- DNS Manager

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: A-Record Exercise
 </p>
Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
 </p>
Connect/log into Client-1 as an admin (mydomain\jane_admin)
 </p>
From Client-1 try to ping “mainframe” notice that it fails
 </p>
Nslookup “mainframe” notice that it fails (no DNS record)
 </p>
Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address
 </p>
<img src="https://imgur.com/4yB3AK8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
Go back to Client-1 and try to ping it. Observe that it works
 </p>
<img src="https://imgur.com/NfemyTj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
- Step 2: Local DNS Cache Exercise
 </p>
Go back to DC-1 and change mainframe’s record address to 8.8.8.8
 </p>
<img src="https://imgur.com/wvf5RI2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address
 </p>
Observe the local dns cache (ipconfig /displaydns)
 </p>
Flush the DNS cache (ipconfig /flushdns) on admin command prompt. Observe that the cache is empty
 </p>
Attempt to ping “mainframe” again. Observe the address of the new record is showing up
 </p>
<img src="https://imgur.com/Gs4ytv8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
- Step 3: CNAME Record Exercise
 </p>
Go back to DC-1 and create a CNAME record that points the host “search” to “www.google.com”
 </p>
<img src="https://imgur.com/KTVAi4Y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
Go back to Client-1 and attempt to ping “search”, observe the results of the CNAME record
</p>
On Client-1, nslookup “search”, observe the results of the CNAME record
 </p>
<img src="https://imgur.com/I5nmVtj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 </p>
