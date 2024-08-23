<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, I observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>
<h3> Building Intuition for DNS</h3>
- Inspect DNS A-Records on the server (hostname to IP address mappings)
- Create a DNS A-record on DC-1 for “mainframe” and have it point to DC-1’s Private IP address
- Flush the DNS cache (ipconfig /flushdns)

<h3>Network File Shares and Permissions</h3>
- Set permissions for the “Domain Users” group:
    - Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
    - Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
    - Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”

