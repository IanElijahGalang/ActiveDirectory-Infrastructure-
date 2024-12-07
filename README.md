# Setting Up Active Directory Infrastructure

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Powershell

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Windows Server 2022</b>


<h2>1. Set up the Domain Controller:</h2>
Create a Resource Group: Organize your resources in Azure.<br>
Create a Virtual Network: Set up a network where your machines will communicate.<br>
Deploy the Domain Controller (DC) Virtual Machine: This VM will be your AD server.<br>
<img width="1512" alt="Resource Group " src="https://github.com/user-attachments/assets/6a9a3fa4-6e98-4a4b-82e3-7bb224b78797">

<h2>2. Set a Static IP Address for the Domain Controller's NIC:</h2>
Change the DC's Private IP to Static:
This ensures the IP won't change if the machine is turned off or restarted.
The DC’s private IP is important because it will act as a DNS server for your client VMs.
<img width="1512" alt="Static" src="https://github.com/user-attachments/assets/4aee81e4-d96b-4436-a96e-547e869c964e">

<h2>3. Disable Windows Firewall on the Domain Controller VM (for testing connectivity):</h2>
Temporarily disable the firewall on the DC VM to make sure no network blocks are in place while testing.
<img width="1512" alt="Firewall" src="https://github.com/user-attachments/assets/44ef0b2c-20cd-4f2f-ae31-f02d377e53d6">

<h2>4. Set the Client VM's DNS to Point to the Domain Controller:</h2>
Configure the Client VM’s DNS settings:
Set the DNS server to the DC's private IP address (not Azure's default DNS).
<img width="1512" alt="Change Client DNS Setting" src="https://github.com/user-attachments/assets/a372423b-5355-4e6e-8791-17f9a6a579d5">

<h2>5. Test the Connection:</h2>
Ping the Domain Controller from the Client VM:
Open a Command Prompt on the Client VM and ping the Domain Controller’s private IP to test connectivity.<br>
Check DNS Settings:
Run ipconfig /all on the Client VM to confirm the DNS server is set to the Domain Controller’s IP address. 
<img width="1512" alt="Ping   ipconfig" src="https://github.com/user-attachments/assets/814465db-3bdf-4e9f-bc13-3a622aaee070">
