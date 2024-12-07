# Setting Up Active Directory Infrastructure


Here's a simplified breakdown of the steps to set up Active Directory:

<h2>1. Set up the Domain Controller:</h2>
Create a Resource Group: Organize your resources in Azure.<br>
Create a Virtual Network: Set up a network where your machines will communicate.<br>
Deploy the Domain Controller (DC) Virtual Machine: This VM will be your AD server.<br>

<h2>2. Set a Static IP Address for the Domain Controller's NIC:</h2>
Change the DC's Private IP to Static:
This ensures the IP won't change if the machine is turned off or restarted.
The DC’s private IP is important because it will act as a DNS server for your client VMs.

<h2>3. Disable Windows Firewall on the Domain Controller VM (for testing connectivity):</h2>
Temporarily disable the firewall on the DC VM to make sure no network blocks are in place while testing.

<h2>4. Set the Client VM's DNS to Point to the Domain Controller:</h2>
Configure the Client VM’s DNS settings:
Set the DNS server to the DC's private IP address (not Azure's default DNS).

<h2>5. Test the Connection:</h2>
Ping the Domain Controller from the Client VM:
Open a Command Prompt on the Client VM and ping the Domain Controller’s private IP to test connectivity.<br>
Check DNS Settings:
Run ipconfig /all on the Client VM to confirm the DNS server is set to the Domain Controller’s IP address. 
