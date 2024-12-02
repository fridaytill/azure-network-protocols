<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this project, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/user-attachments/assets/11cbb902-5902-4351-b949-86bf33f1c077" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/e948c097-8e6c-4ed6-9d4f-f5a56405eee3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/bb719613-4f26-4bd5-b5bb-3c3abf910e24" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Starting out in Microsoft Azure, you want to create a resource group. After you want to create a Windows 10 Virtual Machine and while creating the VM, select the previously created Resource Group. Next you want to create a Linux VM and connect to the SAME resource group. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/2c9efba1-5939-4098-a203-8a646feb4950" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we are going to observe ICMP (Internet Control Message Protocol) Traffic. In your Remote Desktop connect to your Windows 10 Virtual Machine. Withint the VM, install wireshark. Open wireshark and and start a packet capture. Filter for ICMP traffic only. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/098b7b25-f6a1-4410-bbc9-0ab0b7898fe6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/user-attachments/assets/0ecd6f48-2029-4fd0-9aac-9f7b1ffcbf5a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we are going to configure a firewall (Network Security Group). First, you want to initiate a non-stop ping from your Windows 10 VM to your Linux VM. Open Network Security Group in your Linux VM and disable incoming ICMP traffic. Back in Windows 10 VM, observe ICMP traffic in WireShark and the command line Ping Activity. Re-enable ICMP traffic for the Network Security Group for your Linux VM. Back in Windows 10 VM, observe traffic in wireshark and the command line ping activity. Stop ping activity to end observation. 
</p>
<br />

<p>
<img src="https://github.com/user-attachments/assets/9d9f1c74-34e5-4abd-8965-1826165ee732" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we will observe SSH Traffic. Log back into your Windows VM. Open up WireShark. Filter for SSH traffic only. Now you want to "SSH into" your linux virtual machine to observe the traffic via its private ip address. Open powershell and type: ssh labuser@<private IP address>. Typer commands like "username,password,etc" into linux SSH connection and observe the SSH traffic spam in WireShark. 
</p>
<br />
