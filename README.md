<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


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

- Create 2 Virtual Machines within Microsoft Azure. Using a Windows 10 Pro Operating System and Linux.
- Connect to Virtual Machine 1 using Remote Connection, then download & install "WireShark" software.
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/oQI4sfL.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first virtual machine being created in Azure is VM1, The operating system being used is Windows 10 pro
</p>
<br />

<p>
<img src="https://i.imgur.com/PMenivn.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
Notice in the "Networking" tab that the VM created its own subnet and IP address. This is important because although each Virtual Machine will have its own IP address and subnet, Both virtual machines (VM1 & VM2) will have the same Virtual Network.
</p>
<br />

<p>
<img src="https://i.imgur.com/kEG8YZv.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
