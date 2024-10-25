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


<h2>Deployment and Configuration Steps</h2>

<p>
![image](https://github.com/user-attachments/assets/dd456596-3da3-4676-b98e-4efd4e079909)

/>
</p>
<p>
Before diving in, make sure the domain controller VM had a static IP. It's a crucial step - without it, the VMs won't talk to each other properly, even on the same virtual network. Within the Azure portal, find the Networking tab for the domain controller VM, and clicked through to the IP configurations. Then flip the assignment switch to Static and saving. This way, our domain controller has a fixed address that we can rely on for all our future setups.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
With the static IP set, log into the client VM to check connectivity. while running a continuous ping to the domain controller's private IP, it will keep timing out. So, switch to the domain controller VM and tweak the Windows Firewall. Open it up using 'wf.msc', then go to Inbound Rules, and enabled the ICMPv4 echo request rules. Back on the client VM, the ping start working. This is a small step, but crucial for making sure our VMs can talk to each other.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To install Active Directory on the domain controller VM, open Server Manager and select "Add Roles and Features." After confirming the VM's private IP address, choose "Active Directory Domain Services" in the Server Roles tab, add the required features, and complete the installation. To promote the server to a domain controller, click the warning flag in Server Manager and select "Promote this server to a domain controller." Create a new forest by specifying a domain name (This can be a domain name of your choosing), set a domain password, and proceed through the installation screens. This process establishes the foundation for the Active Directory environment.
</p>
<br />







<h2>Key Takeaways</h2>


Setting up Active Directory in Azure requires careful network configuration, including assigning a static IP to the domain controller and enabling ICMP traffic through the Windows Firewall. The core process involves installing Active Directory Domain Services and promoting the server to a domain controller. These steps create a foundation for a functional Active Directory environment in the cloud, paving the way for future expansions and integrations.
