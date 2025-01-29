# Virtual Enterprise Creation

This repository serves as a detailed guide and resource for setting up and managing a Virtual Enterprise environment using a Domain Controller. It includes the setup of Active Directory Domain Services, user management, system testing, and troubleshooting methods. Additionally, this project focuses on automating parts of the process, ensuring efficient and secure administration for an enterprise environment.

## Table of Contents

- [Overview](#overview)
- [Project Structure](#projectstructure)
- [Setup Instructions](#setupinstructions)
- [Testing](#testing)
- [Common Issues & Troubleshooting](#common-issues-&-troubleshooting)

## Overview

This project focuses on building a complete **Virtual Enterprise Environment** that can be used for learning purposes or as a base for real-world enterprise setups. It involves several key components:

1. **Domain Controller Setup**: Setting up Active Directory, DNS, and the Domain Controller on a Windows Server 2022 instance.
2. **User Management**: Creating, managing, and automating the management of user accounts within the Active Directory.
3. **Testing**: Running tests to ensure the Domain Controller, user accounts, and DNS functions are operating properly.
4. **Notes**: Maintaining a record of troubleshooting steps, ideas, and known issues encountered during the setup.

## Project Structure

This repository is organized into the following folders, each focusing on a different part of the setup process:

- **[DomainControllerSetup](./DomainControllerSetup)**: All the necessary steps, scripts, and configurations for setting up the Domain Controller, including Active Directory Domain Services (AD DS) installation, DNS configuration, and domain promotion.
- **[UserManagement](./UserManagement)**: Guides and scripts for managing user accounts in Active Directory, including user creation, password management, and group assignments.
- **[Testing](./Testing)**: Test cases, scripts, and methods to verify that your domain controller and user management processes work as expected. This includes DNS verification, AD replication, and logon tests.
- **[Notes](./Notes)**: A collection of notes, troubleshooting tips, to-do lists, and other resources to assist with setup or to maintain the system post-configuration.

## Setup Instructions

To set up the Virtual Enterprise environment, follow these general instructions:

1. **Prepare Your Environment**:
   - Ensure you have a VM with Windows Server 2022 installed and properly configured.
   - You may need to allocate static IP addresses to ensure that your Domain Controller is easily reachable.

2. **Domain Controller Setup**:
   - Follow the instructions in the **[DomainControllerSetup](./DomainControllerSetup)** folder to install Active Directory Domain Services (AD DS) and promote your server to a Domain Controller.

3. **User Management**:
   - After setting up the Domain Controller, move on to **[UserManagement](./UserManagement)** to begin adding users, assigning roles, and managing passwords.

4. **Testing**:
   - Verify that everything is working by running the tests in the **[Testing](./Testing)** folder.

5. **Troubleshooting**:
   - If you run into issues, check the **[Notes](./Notes)** folder for known issues and troubleshooting steps.

6. **Post-Setup Maintenance**:
   - After setup, use the **UserManagement** and **Testing** folders to manage users and verify system functionality periodically.

## Testing

Testing is critical for ensuring that the Domain Controller and user management systems function as expected. The **[Testing](./Testing)** folder contains a series of steps and scripts to help verify that everything works after initial setup.

Some of the key tests include:

- **DNS Resolution**: Ensure the Domain Controller’s DNS server is functioning correctly.
- **Active Directory Replication**: Verify that changes made to the Domain Controller are propagated across the network.
- **User Login Tests**: Ensure that users can successfully log in to domain-joined machines.
- **Group Policy Application**: Test if Group Policies are applied to machines and users correctly.

## Common Issues & Troubleshooting

During the setup and maintenance of the Virtual Enterprise environment, you may run into several issues. This section includes common problems and troubleshooting steps.

### 1. **DNS Issues**:
   - **Problem**: Machines are unable to resolve domain names.
   - **Solution**: Ensure that the Domain Controller is set as the primary DNS server for your network.
   - **Commands to Run**:
     ```bash
     nslookup <your-domain-name>
     ```
     This should return the IP address of the Domain Controller.

### 2. **User Logon Failures**:
   - **Problem**: Users cannot log into the domain.
   - **Solution**: Verify that the user account exists and is not locked out. Also, ensure that the machine is connected to the domain and can communicate with the Domain Controller.
   - **Commands to Run**:
     ```bash
     Test-Connection -ComputerName DC01
     ```

### 3. **Active Directory Replication Failures**:
   - **Problem**: Changes made to AD are not replicating to other Domain Controllers.
   - **Solution**: Check replication status using the `repadmin` tool and ensure there are no network/firewall issues preventing replication.
   - **Commands to Run**:
     ```bash
     repadmin /showrepl
     ```

For more troubleshooting, see the **[Notes](./Notes)** folder.
