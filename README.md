<img src="https://i.imgur.com/2JQawfN.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
Within Wireshark, I filtered for ICMP (Internet Control Message Protocol) traffic and opened PowerShell to execute a command ping. Ping utilizes ICMP, which is used by devices in a network to communicate problems within data transmition. I used ping to see if I can communicate with the Ubuntu VM using its private IP address and with google.com. Afterwards, I used a perpetual ping to the Ubuntu VM in order to see how network security groups work. I executed the perpetual ping with the command: ping -t (ip address).
Within Wireshark, I filtered for ICMP (Internet Control Message Protocol) traffic and opened PowerShell to execute a command called ping. Ping utilizes ICMP, which is used by devices in a network to communicate problems within data transmition. I used ping to see if I can communicate with the Ubuntu VM using its private IP address and with google.com. Afterwards, I used a perpetual ping to the Ubuntu VM in order to see how network security groups work. I executed the perpetual ping with the command: ping -t (ip address).
</p>
<br />

@@ -86,10 +86,10 @@ To observe DNS traffic, I used the filter udp.port == 53 and the command nslooku
<img src="https://i.imgur.com/N7voXYU.png" height="80%" width="80%" alt="Azure Networking Steps"/>
</p>
<p>
To finish my lab, I decided to see RDP traffic. The filter for Wireshark is tcp.port == 3389. There is non-stop traffic because RDP is constantly showing me a live stream from one computer to another (in my case, my computer accessing the VM that is hosted on Azure) and thus traffic is always transmitted. 
To finish my lab, I decided to observe RDP traffic. The filter for Wireshark is tcp.port == 3389. There is non-stop traffic because RDP is constantly showing me a live stream from one computer to another (in my case, my computer accessing the VM that is hosted on Azure) and thus traffic is always transmitted. 
</p>
<br />

<h2>Final Notes</h2>
<h2>Lessons Learned </h2>

The purpose of this lab is for me to see how different protocols and ports are utilized in a network between devices. While this lab does not exactly allow me to troubleshoot, it still serves a purpose to gather information. While troubleshooting, I need to utilize different tools like Wireshark and the command line to see how traffic flows in a network through ports and protocols. Familiarity and an inquisitive mind are key to success!
