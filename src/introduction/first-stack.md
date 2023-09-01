# Creating Your First Stack

## 3. Creating Your First Stack

Now that you have Pulumi installed and your Azure credentials configured, it's time to create your first Pulumi stack. A stack is a deployment target for your infrastructure code. You can think of it as an isolated environment where your resources will be provisioned.

**Steps:**
1. **Create a New Stack**: In your Pulumi project directory, create a new stack using the following command:
   
    ```bash
    pulumi stack init my-first-stack
    ```

    This command initializes a new stack named `my-first-stack`. You can choose any name that makes sense for your project.

2. **Initialize Your Stack**: Before defining your Azure resources, you need to initialize your stack. This step sets up the necessary configuration for your project.

    ```bash
    pulumi up
    ```

    Follow the prompts to log in to your Azure account if prompted.

3. **Define Your Azure Resources**: In your Pulumi project directory, open the `index.ts` file. This is where you'll define your Azure resources using TypeScript.

    Here's a simple example that creates an Azure Storage Account:

    ```typescript
    import * as pulumi from "@pulumi/pulumi";
    import * as azure from "@pulumi/azure";

    const storageAccount = new azure.storage.Account("mystorageaccount", {
        resourceGroupName: resourceGroup.name,
        accountReplicationType: "LRS",
        accountTier: "Standard",
    });
    ```

    You can define various Azure resources like virtual machines, databases, storage accounts, and more using the `@pulumi/azure` library.

4. **Preview and Deploy**: After defining your resources, it's time to preview the changes and deploy them to Azure.

    ```bash
    pulumi up
    ```

    Pulumi will analyze your code, show you the changes it's about to make, and prompt you for confirmation. Review the changes carefully, and if everything looks good, confirm the deployment.

Congratulations! You've just created and deployed your first Azure resources using Pulumi. In the next section, we'll delve deeper into defining infrastructure with code.
