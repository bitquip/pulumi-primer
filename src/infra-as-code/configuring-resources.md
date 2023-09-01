# Configuring Resources

### 4.2 Configuring Resources

You can configure resource properties using TypeScript objects. For instance, configuring a storage container:

```typescript
const storageContainer = new azure.storage.Container("mycontainer", {
    storageAccountName: storageAccount.name,
    containerAccessType: "private",
});
```

Here, we're creating a private storage container within the previously created storage account.