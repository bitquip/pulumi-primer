# Creating Resources

### 4.1 Creating Resources

In Pulumi, you can create resources using classes provided by the Azure library. Here's an example of creating an Azure Storage Account:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const storageAccount = new azure.storage.Account("mystorageaccount", {
    resourceGroupName: resourceGroup.name,
    accountReplicationType: "LRS",
    accountTier: "Standard",
});
```

In this example, we're creating an Azure Storage Account named "mystorageaccount" in the same resource group as defined earlier. The `accountReplicationType` specifies the replication type, and `accountTier` defines the performance tier of the storage account.
