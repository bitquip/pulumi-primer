# Conclusion

```typescript
import * as azure from "@pulumi/azure";

// Define an Azure Resource Group
const resourceGroup = new azure.core.ResourceGroup("myResourceGroup", {
    location: "East US",
});

// Define an Azure Virtual Network
const virtualNetwork = new azure.network.VirtualNetwork("myVnet", {
    resourceGroupName: resourceGroup.name,
    addressSpaces: ["10.0.0.0/16"],
    subnets: [
        {
            name: "subnet-1",
            addressPrefix: "10.0.1.0/24",
        },
        {
            name: "subnet-2",
            addressPrefix: "10.0.2.0/24",
        },
    ],
});

// Define an Azure Virtual Machine
const virtualMachine = new azure.compute.VirtualMachine("myVm", {
    resourceGroupName: resourceGroup.name,
    vmSize: "Standard_A0",
    networkInterfaceIds: [networkInterface.id],
    osProfile: {
        computerName: "hostname",
        adminUsername: "adminuser",
        adminPassword: "Password1234!",
    },
    storageOsDisk: {
        name: "osdisk",
        createOption: "FromImage",
        caching: "ReadWrite",
    },
    storageImageReference: {
        publisher: "Canonical",
        offer: "UbuntuServer",
        sku: "18.04-LTS",
        version: "latest",
    },
});

// Define an Azure Storage Account
const storageAccount = new azure.storage.Account("mystorage", {
    resourceGroupName: resourceGroup.name,
    accountReplicationType: "LRS",
    accountTier: "Standard",
});

// Define an Azure Function App
const functionApp = new azure.appservice.FunctionApp("myFunctionApp", {
    resourceGroupName: resourceGroup.name,
    appServicePlanId: appServicePlan.id,
    version: "~3",
    storageAccountName: storageAccount.name,
    osType: "Linux",
    runtime: "node",
});
```