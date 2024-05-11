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

 <h3>Observe ICMP Traffic</h3>
 
 - Log into Windows 10 Virtual Machine using remote desktop connection
 - Download and Install Wireshark (https://www.wireshark.org/download.html)
    - Install Windows 64 bit version
    - Install Wireshark by default settings
  - Open Wireshark and double click Ethernet Adapter.  Wireshark should display live traffic on Virtual Machine

<p>
<br />
<img src="https://i.imgur.com/nFjvdII.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


 - Type icmp in the text box containing "Apply a display filter" and press enter
 - This command will filter traffic by icmp.  No traffic should appear on Wireshark

<p>
<br />
<img src="https://i.imgur.com/eV3LyQ1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />


 - Go back to Azure Portal to capture VM2 private ip address
  - Type Virtual Machine in Azure search box, click VM2, notice the private ip address in Networking section

<p>
<br />
<img src="https://i.imgur.com/XbM5bwW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

- Return to VM1
- Open Windows Powershell
 - Ping VM2 using its private address.  Notice the Response

</p>
<br />
<img src="https://i.imgur.com/xEoLZbh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 - Notice icmp traffic on Wireshark
   
</p>
<br />
<img src="https://i.imgur.com/sxiz0zf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
- Ping www.google.com -4.  Notice icmp traffic on Wireshark

<p>
<br />
<img src="https://i.imgur.com/ck5F7Sn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Clear Wireshark data by clicking the green icon on the upper left of Window (restart current capture)
   - Click "continue without saving"
   - Wireshark data should be cleared
 

     
 <h3>Observe SSH Traffic</h3>

  - Go back to Wireshark and filter traffic for ssh
  - Go back to Windows Powershell and type ssh (vm2 username @ vm2 ip address)" and press enter
     - Example:  ssh labuser@10.0.0.0.5
   - Type "yes" to "are you sure you want to continue connecting".
   - Enter VM2 Password and notice ssh traffic in Wireshark

<p>
<br />
<img src="https://i.imgur.com/chX1w25.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 - Type "exit" to close the connection
 - Clear Wireshark data by clicking the green icon on the upper left of Window (restart current capture)
   - Click "continue without saving"
   - Wireshark data should be cleared



 <h3>Observe DHCP Traffic</h3>

  - Go back to Wireshark and filter traffic for "dhcp"
  - Go back to Windows Powershell and type "ipconfig /renew" and press enter
  - Notice dhcp traffic in Wireshark

<p>
<br />
<img src="https://i.imgur.com/IdYMafK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 - Clear Wireshark data by clicking the green icon on the upper left of Window (restart current capture)
   - Click "continue without saving"
   - Wireshark data should be cleared



 <h3>Observe DNS Traffic</h3>

  - Go back to Wireshark and filter traffic for "dns"
  - Go back to Windows Powershell and type "nslookup www.google.com" and press enter
  - Notice dns traffic in Wireshark

<p>
<br />
<img src="https://i.imgur.com/p9hvNbL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
 - Clear Wireshark data by clicking the green icon on the upper left of Window (restart current capture)
   - Click "continue without saving"
   - Wireshark data should be cleared


  


