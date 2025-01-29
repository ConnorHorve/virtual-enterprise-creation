# Domain Controller Setup

This folder contains all the steps, scripts, and configurations necessary to set up a Domain Controller (DC) for a Virtual Enterprise environment.

## Steps to Set Up the Domain Controller

1. **Install Windows Server**: Ensure that Windows Server 2022 is installed on your VM.
2. **Install VMware Tools**: Install VMware Tools for optimal performance of your virtual machine.
3. **Set a Static IP**: Configure a static IP address for the DC.
4. **Install Active Directory Domain Services (AD DS)**:
   - Open **Server Manager** > **Add Roles and Features**.
   - Select **Active Directory Domain Services** and install it.
5. **Promote to Domain Controller**:
   - After installation, use **Server Manager** to promote the server to a Domain Controller.
   - Choose to create a new forest and domain (e.g., `example.local`).
6. **Configure DNS**:
   - The Domain Controller should also be configured as the DNS server for proper name resolution within the domain.
7. **Reboot**: After the promotion, the server will need to restart.

## Notes

- Ensure the server's IP is set as the DNS server for the network to avoid issues with domain connectivity.
- The Domain Controller can later be joined to the domain by other machines and VMs.
