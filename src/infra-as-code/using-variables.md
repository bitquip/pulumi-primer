# Using Variables

### 4.3 Using Variables

You can use variables to make your code more dynamic. For example, defining a variable for the storage account name:

```typescript
const storageAccountName = "mystorageaccount";

const storageAccount = new azure.storage.Account(storageAccountName, {
    // ...
});
```

This allows you to change the storage account name easily without modifying the resource definition.

In the next sections, we'll explore more advanced topics like managing multiple stacks, handling configuration, and updating stacks.

---

Stay tuned for the upcoming sections where we'll explore advanced Pulumi concepts and work on real-world scenarios using Pulumi with Azure!