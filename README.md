## learn-bicep-arm-templates

My working through the Microsoft Docs learning path for [Deploy and manage resources in Azure by using Bicep](https://docs.microsoft.com/en-us/learn/paths/bicep-deploy/) and associated learning paths.

Playground at https://aka.ms/bicepdemo (official) or https://playgroundbicep.azurewebsites.net/ (community hosted).

Install Bicep manually after installing Azure PowerShell. See [Instructions](https://docs.microsoft.com/en-us/azure/azure-resource-manager/bicep/install#windows).

Connect:

```powershell
Get-AzSubscription
```

```powershell
$context = Get-AzSubscription -SubscriptionId {subscription Id}
Set-AzContext $context
```

If using training sandbox:

```powershell
$context = Get-AzSubscription -SubscriptionName 'Concierge Subscription'
Set-AzContext $context
```

Then:

```powershell
Set-AzDefault -ResourceGroupName {resource group Id}
```

Deploy:

```powershell
New-AzResourceGroupDeployment -TemplateFile main.bicep -environmentType nonprod
```

View deployments:

```powershell
Get-AzResourceGroupDeployment -ResourceGroupName {resource group Id} | Format-Table
```

