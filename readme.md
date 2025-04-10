# Azure PowerShell Command Reference

Azure PowerShell offers a wide range of commands for managing Azure resources, and it has evolved significantly with the introduction of the Az module. Below is a comprehensive list of common Azure PowerShell commands (cmdlets) with their usage.

---

## 1. Account Management

### Connect-AzAccount
**Usage**: Authenticates and connects to your Azure account.
```bash
Connect-AzAccount
```

### Get-AzSubscription
**Usage**: Lists all the Azure subscriptions associated with the account.
```bash
Get-AzSubscription
```

### Select-AzSubscription
**Usage**: Selects a specific subscription to work with.
```bash
Select-AzSubscription -SubscriptionId "your-subscription-id"
```

### Disconnect-AzAccount
**Usage**: Disconnects the current session from Azure.
```bash
Disconnect-AzAccount
```

### Update-Module
**Usage**: Updates the Az module to the latest version.
```bash
Update-Module -Name Az
```

### Get-AzVersion
**Usage**: Gets the version of the Az module.
```bash
Get-AzVersion
```

## 2. Resource Group Management

### New-AzResourceGroup
**Usage**: Creates a new resource group.
```bash
New-AzResourceGroup -Name "MyResourceGroup" -Location "EastUS"
```

### Get-AzResourceGroup
**Usage**: Lists all resource groups in the current subscription.
```bash
Get-AzResourceGroup
```

### Get-AzResourceGroupDeployment
**Usage**: Lists all deployments in a specific resource group.
```bash
Get-AzResourceGroupDeployment -ResourceGroupName "MyResourceGroup"
```

### Remove-AzResourceGroup
**Usage**: Removes a specific resource group.
```bash
Remove-AzResourceGroup -Name "MyResourceGroup" -Force
```

### New-AzResource
**Usage**: Creates a new resource in a specific resource group.
```bash
New-AzResource -ResourceGroupName "MyResourceGroup" -Name "MyResource" -Location "EastUS" -ResourceType "Microsoft.Compute/virtualMachines" -Properties $properties
```

### Get-AzResource
**Usage**: Lists all resources in a specific resource group.
```bash
Get-AzResource -ResourceGroupName "MyResourceGroup"
```

### Get-AzResourceById
**Usage**: Retrieves a resource by its ID.
```bash
Get-AzResourceById -ResourceId "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/{resourceType}/{resourceName}"
```

### Set-AzResource
**Usage**: Updates a resource with new properties.
```bash
Set-AzResource -ResourceId $resourceId -Properties $newProperties
```

### Remove-AzResource
**Usage**: Removes a specific resource by its ID.
```bash
Remove-AzResource -ResourceId "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/{resourceType}/{resourceName}" -Force
```

### New-AzStorageAccount
**Usage**: Creates a new storage account in a specific resource group.
```bash
New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "EastUS" -SkuName "Standard_LRS"
```

## 4. Virtual Machine (VM) Management

### New-AzVM
**Usage**: Creates a new Azure virtual machine.
```bash
New-AzVM -ResourceGroupName "MyResourceGroup" -Location "EastUS" -VM $vmConfig
```

### New-AzVM
**Usage**: Creates a new virtual machine in a specific resource group.
```bash
New-AzVM -ResourceGroupName "MyResourceGroup" -Location "EastUS" -VM $vmConfig
```

### Start-AzVM
**Usage**: Starts a virtual machine in a specific resource group.
```bash
Start-AzVM -ResourceGroupName "MyResourceGroup" -Name "MyVM"
```

### Stop-AzVM
**Usage**: Stops a virtual machine in a specific resource group.
```bash
Stop-AzVM -ResourceGroupName "MyResourceGroup" -Name "MyVM" -Force
```

### Restart-AzVM
**Usage**: Restarts a virtual machine in a specific resource group.
```bash
Restart-AzVM -ResourceGroupName "MyResourceGroup" -Name "MyVM"
```

### Remove-AzVM
**Usage**: Removes a virtual machine in a specific resource group.
```bash
Remove-AzVM -ResourceGroupName "MyResourceGroup" -Name "MyVM"
```
## 5. Storage Account Management
New-AzStorageAccount
**Usage**: Creates a new Azure Storage Account.
```bash
New-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -Location "EastUS" -SkuName "Standard_LRS"
```

### Get-AzStorageAccount
**Usage**: Lists all storage accounts in a specific resource group.
```bash
Get-AzStorageAccount -ResourceGroupName "MyResourceGroup"
```

### Set-AzStorageAccount
**Usage**: Updates the SKU of a storage account in a specific resource group.
```bash
Set-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount" -SkuName "Standard_GRS"
```

### Remove-AzStorageAccount
**Usage**: Removes a specific storage account in a specific resource group.
```bash
Remove-AzStorageAccount -ResourceGroupName "MyResourceGroup" -AccountName "mystorageaccount"
```
## 6. Azure Networking
**Usage**: Deletes a storage account.
```bash 
New-AzVirtualNetwork -ResourceGroupName "MyResourceGroup" -Location "EastUS" -Name "MyVNet" -AddressPrefix "10.0.0.0/16"
```

### Get-AzVirtualNetwork
**Usage**: Lists all virtual networks in a specific resource group.
```bash
Get-AzVirtualNetwork -ResourceGroupName "MyResourceGroup"
```

### New-AzNetworkSecurityGroup
**Usage**: Creates a new network security group in a specific resource group.
```bash
New-AzNetworkSecurityGroup -ResourceGroupName "MyResourceGroup" -Location "EastUS" -Name "MyNSG"
```

### Get-AzNetworkSecurityGroup
**Usage**: Lists all network security groups in a specific resource group.
```bash
Get-AzNetworkSecurityGroup -ResourceGroupName "MyResourceGroup"
```

### New-AzPublicIpAddress
**Usage**: Creates a new public IP address in a specific resource group.
```bash
New-AzPublicIpAddress -ResourceGroupName "MyResourceGroup" -Location "EastUS" -Name "MyPublicIP" -AllocationMethod Dynamic
```

### Get-AzPublicIpAddress
**Usage**: Lists all public IP addresses in a specific resource group.
```bash
Get-AzPublicIpAddress -ResourceGroupName "MyResourceGroup"
```
## 7. Azure Active Directory (AAD)
Get-AzADUser
**Usage**: Retrieves user details from Azure Active Directory.

```bash
Get-AzADUser -UserPrincipalName "user@domain.com"
```

### New-AzADUser
**Usage**: Creates a new user in Azure Active Directory.
```bash
New-AzADUser -UserPrincipalName "newuser@domain.com" -DisplayName "New User" -Password "P@ssword123!"
```

### Remove-AzADUser
**Usage**: Removes a user from Azure Active Directory.
```bash
Remove-AzADUser -UserPrincipalName "user@domain.com"
```

### Get-AzADGroup
```bash
Get-AzADGroup
```

## 8. Azure Backup
Get-AzRecoveryServicesVault
**Usage**: Lists all Recovery Services Vaults.
```bash
Get-AzRecoveryServicesVault
```

### New-AzRecoveryServicesVault
**Usage**: Creates a new Recovery Services Vault in a specific resource group.
```bash
New-AzRecoveryServicesVault -ResourceGroupName "MyResourceGroup" -Location "EastUS" -Name "MyRecoveryVault"
```

### Enable-AzRecoveryServicesBackup
**Usage**: Enables backup for a specific resource.
```bash
Enable-AzRecoveryServicesBackup -ResourceId "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/{resourceType}/{resourceName}"
```

## 9. Azure Monitor & Logging
Get-AzLog
**Usage**: Gets activity logs for your subscription.

```bash
Get-AzLog -StartTime (Get-Date).AddDays(-7) -EndTime (Get-Date)
```
## 10. Other Useful Commands
Get-Help
**Usage**: Displays help for any cmdlet.
```bash
Get-Help New-AzVM
```
```bash
git add README.md