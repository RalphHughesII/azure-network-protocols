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
- Assign both machines to the same Subnet

<h2>Prerequisites </h2>

- Create a Windows 10 Virtual Machine using Azure 
- Create an Ubuntu Server Virtual Machine using Azure 


<h2>Actions and Observations</h2>

 - Log into Windows 10 Virtual Machine using remote desktop connection
 - Download and Install Wireshark (https://www.wireshark.org/download.html)
    - Install Windows 64 bit version
    - Install Wireshark by default settings
  - Open Wireshark and double click Ethernet Adapter.  Wireshark should display live traffic on Virtual Machine


<p>
<img src="https://i.imgur.com/nFjvdII.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 - Type icmp in the text box containing "Apply a display filter" and press enter
 - This command will filter traffic by icmp.  No traffic should appear on Wireshark
   

 <img src="https://i.imgur.com/eV3LyQ1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
 - Go back to Azure Portal to capture VM2 private ip address
  - Type Virtual Machine in Azure search box, click VM2, notice the private ip address in Networking section
<p>
<img src="https://i.imgur.com/XbM5bwW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
