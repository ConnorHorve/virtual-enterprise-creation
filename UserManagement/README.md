# User Management

This folder contains guides and scripts for adding, managing, and deleting users in the domain using Active Directory.

## Steps for User Management

1. **Create a User**:
   - Open **Active Directory Users and Computers**.
   - Right-click on **Users** and select **New** > **User**.
   - Provide the necessary details (e.g., username, password) and finish the creation process.

2. **Assign Permissions**:
   - After creating a user, you can assign the user to groups or configure specific permissions based on the role.

3. **Password Management**:
   - You can reset passwords through **Active Directory Users and Computers** by right-clicking on the user and selecting **Reset Password**.

4. **User Scripts**:
   - This folder contains scripts that automate user creation, modification, and deletion in bulk using PowerShell.
   - Example:
   ```powershell
   New-ADUser -Name "John Doe" -GivenName "John" -Surname "Doe" -SamAccountName "jdoe" -UserPrincipalName "jdoe@corp.local" -Path "CN=Users,DC=corp,DC=local" -AccountPassword (ConvertTo-SecureString "Password123" -AsPlainText -Force) -Enabled $true
