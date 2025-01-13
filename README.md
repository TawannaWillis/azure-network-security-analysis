<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Inspecting Traffic Between Azure Virtual Machines</h1>

<br /><h2>Objectives</h2>

Analyze network traffic between Azure virtual machines using Wireshark.<br />
Test and configure network security groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop Connection
- Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (21H2)
- Ubuntu Server 20.04

<h2>Environment Prep</h2>

<br />-Set up two VMs in Azure within the same virtual network.<br />
<br />-Configure one VM with Windows 10 Pro and the other with Ubuntu.<br />
<br />-Use the Windows VM to connect to the Ubuntu VM via command line or PowerShell.<br /> 

<h2>Actions and Steps</h2>

<p>
<img src="https://i.imgur.com/DutP0XT.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Connect to the Windows VM via Remote Desktop using its public IP.<br />
<br />-Install Wireshark to begin analyzing network traffic.<br />
</p>
<br />

<p>
<img src="https://i.imgur.com/2JQawfN.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Apply a filter for ICMP traffic in Wireshark.<br />
<br />-Open PowerShell and run the ping command to test network communication.<br />
<br />-Test communication with the Ubuntu VM using its private IP and with google.com.<br />
<br />-Initiate a continuous ping to the Ubuntu VM using: ping -t (IP address) to observe network security groups.<br />
</p>
<br />

<p>
<img src="https://i.imgur.com/HTga2Iq.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Access the networking settings for the Ubuntu VM in the Azure portal.<br />
<br />-Create an inbound security rule to block ICMP traffic.<br />
<br />-Set the rule's priority higher than SSH (300) to ensure it takes precedence.<br /> 
</p>
<br />

<p>
<img src="https://i.imgur.com/i3BC2LW.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Open the Azure portal and configure networking settings for the Ubuntu VM.<br />
<br />-Add an inbound security rule to block ICMP traffic, setting priority above SSH (300).<br />
<br />-Check the Windows VM and confirm ICMP traffic is blocked.<br />
<br />-Modify the rule to allow ICMP traffic.<br />
<br />-Run the continuous ping to ensure it resolves without timeouts.<br />
</p>
<br />

<p>
<img src="https://i.imgur.com/fDtuLo9.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Examine SSH traffic by logging into the Ubuntu server via PowerShell using the ssh command.<br />
<br />-Filter SSH traffic in Wireshark with tcp.port == 22.<br />
<br />-View session activity in Wireshark, where each command executed on the Ubuntu server is logged.<br />
</p>
<br />

<p>
<img src="https://i.imgur.com/mptFClI.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Exit the Ubuntu server to filter for DHCP traffic.<br />
<br />-Attempt to issue a new IP address from the VM using the ipconfig /renew command.<br />
<br />-Note that the command temporarily disconnects for a few seconds.<br />
<br />-After reconnecting, observe the resulting DHCP traffic in Wireshark.<br />
</p>
<br />

<p>
<img src="https://i.imgur.com/gtiupfH.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Filter DNS traffic in Wireshark using udp.port == 53.<br />
<br />-Use the nslookup command to query google.com and disney.com.<br />
<br />-Observe the results of the DNS lookup for these popular sites.<br /> 
</p>
<br />

<p>
<img src="https://i.imgur.com/N7voXYU.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
<br />-Filter RDP traffic in Wireshark using tcp.port == 3389.<br />
<br />-Observe continuous traffic as RDP streams live data between the computer and the VM hosted on Azure.<br />
</p>
<br />

<h2>Lessons Learned </h2>

The goal of the lab was to observe how different protocols and ports are used in network communication between devices.
Although the lab didn’t focus on troubleshooting, it provided valuable information.
I learned that troubleshooting requires tools like Wireshark and the command line to understand how traffic flows through network ports and protocols.
I realized that success in troubleshooting depends on both familiarity with the tools and maintaining an inquisitive mindset.
