<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, DNS, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create 2 Virtual Machines (VM1 & VM2) within Microsoft Azure. Using a Windows 10 Pro Operating System and Linux.
- Connect to Virtual Machine #1 using Remote Connection, then download & install "WireShark" software.
- Test Connectivity of Virtual Machine #2 using the Command Line and notice ICMP traffic in WireShark.
- Create a firewall setting for Virtual Machine #2 in Microsoft Azure to stop all incomning ICMP traffic. 
- Securely connect to Virtual machine #2 using Secure Shell protocol in VM1's powershell. Check SSH traffic in WireShark.
- Use Command lines in Microsoft PowerShell to check DNS traffic in WireShark.

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/oQI4sfL.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- The first virtual machine being created in Azure is VM1, The operating system being used is Windows 10 pro
</p>
<br />

<p>
<img src="https://i.imgur.com/PMenivn.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Notice in the "Networking" tab that the VM created its own subnet and IP address. This is important because although each Virtual Machine will have its own IP address and subnet, Both virtual machines (VM1 & VM2) will have the same Virtual Network.
</p>
<br />

<p>
<img src="https://i.imgur.com/kEG8YZv.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- The 2nd virtual machine being created in Azure is VM2. The operating system being used is Linux (Ubuntu 20.04)
</p>
<br />

<p>
<img src="https://i.imgur.com/6JDj8tq.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- These are the current resources we now have setup inside of Azure.  2 Virtual Machines, 2 Virtual NIC's, 2 Network Security Groups, 2 public IP addresses, and 1 Virtual Network connecting both VM's.
</p>
<br />

<p>
<img src="https://i.imgur.com/dMj9wKX.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Once you've connected into VM1's Remote desktop, Connect to the internet to Download the "WireShark" software then install it unto VM1.
</p>
<br />

<p>
<img src="https://i.imgur.com/LQoeyv9.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Open the "WireShark" application once it finish installing. Double Click on the "Ethernet adapter" Option to start seeing the live data traffic that's happening on the virtual machine. The Blue icon in the top left corner should turn red when traffic is passing through.
</p>
<br />


<p>
<img src="https://i.imgur.com/1nMJJh3.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- As you can see, the ICMP traffic shows up on WireShark when you test the Connectivity of VM2. On the command line its continuing to send packets beccause VM2's network security group is allowing inbound ICMP traffic to come through.
</p>
<br />

<p>
<img src="https://i.imgur.com/WXXhWEq.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- In the Azure Portal you can configure the Network security group settings to stop ICMP traffic from getting to VM2. By denying all inbound ICMP traffic, the Ping connectivity from VM1's command line will cease.
</p>
<br />

<p>
<img src="https://i.imgur.com/yV9Z675.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Now that the rules are changed lets see what happens on WireShark and Command Line.
</p>
<br />

<p>
<img src="https://i.imgur.com/1Erg7ii.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- As you can see the connectivity between the two virtual machines dropped, so basically whats happening here is that the Ping signal thats being sent from VM1's command line is being blocked by VM2's firewall or network security group.
</p>
<br />


<p>
<img src="https://i.imgur.com/xh8H7U3.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Using Secure Shell protocol in "Windows Power Shell" to connect to VM2's command line.
</p>
<br />

<p>
<img src="https://i.imgur.com/P2EeZkk.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
- In Power Shell when you type "nslookup" + the name of a website you can see DNS traffic being sent on WireShark. This is because a DNS translates domain names to IP addresses so browsers can load Internet resources.
</p>
<br />
