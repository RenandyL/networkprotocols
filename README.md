<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Inspecting Traffic Between Azure Virtual Machines and Network Security Groups (NSGs)</h1>
In this tutorial, build intuition for DNS, and experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>
<h3> Building Intuition for DNS</h3>
<p> - Inspect DNS A-Records on the server (hostname to IP address mappings)</p>
<p> - Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address</p>
<p> - Flush the DNS cache (ipconfig /flushdns)</p>
<br/>

<h3> Local DNS Cache</h3>
<p> - In the domain controller, change the mainframe's record address to 8.8.8.8</p>
<p> - In another VM, ping “mainframe” again and observe it still pings the old address</p>
<p> - Observe the local DNS cache (ipconfig /displaydns)</p>
<p> - Flush the DNS cache (ipconfig /flushdns) and observe that the cache is empty</p>
<p> - Attempt to ping “mainframe” again and observe the address of the new record is showing up</p>
<br/>

<h3>Network File Shares and Permissions</h3>
<h4> - Set permissions for the “Domain Users” group:</h4>
   <p> - Folder: “read-access”, Group: “Domain Users”, Permission: “Read”</p>
   <p> - Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”</p>
   <p> - Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”</p>
<br/>
