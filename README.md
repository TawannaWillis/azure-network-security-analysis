<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
In this lab, I set up Active Directory on Azure as a foundation for future projects. I'm using two VMs on the same virtual network, but today I'm just focusing on one - turning it into our domain controller. The other VM will join as a client later. It's a creative way to create a mini-network in the cloud and get hands-on with Active Directory.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services


<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1. Set Domanin Controller IP Address To Static
- Step 2. Check Connectivity From Client To Domain Controller
- Step 3. Install Active Directory On Domain Controller
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before diving in, I had to make sure the domain controller VM had a static IP. It's a crucial step - without it, the VMs won't talk to each other properly, even on the same virtual network. Within the Azure portal, I found the Networking tab for the domain controller VM, and clicked through to the IP configurations. Then, it was just a matter of flipping the assignment switch to Static and saving. This way, our domain controller has a fixed address that we can rely on for all our future setups.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
With the static IP set, I logged into the client VM to check connectivity. I ran a continuous ping to the domain controller's private IP, but it kept timing out. So, I switched to the domain controller VM and tweaked the Windows Firewall. I opened it up using 'wf.msc', went to Inbound Rules, and enabled the ICMPv4 echo request rules. Back on the client VM, the ping started working like a charm. It's a small step, but crucial for making sure our VMs can talk to each other.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
