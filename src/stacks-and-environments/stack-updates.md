# Stack Updates

### 5.3 Stack Updates

#### Updating Stacks

As your infrastructure requirements evolve, you'll need to update your stacks. Pulumi makes this process straightforward.

1. Make changes to your Pulumi code.
2. Run:

   ```bash
   pulumi up
   ```

   Pulumi analyzes the changes and prompts you to confirm the update. It applies only the necessary changes to reach the desired state.

#### Benefits of Stack Updates

- **Efficiency**: Pulumi updates only what has changed, avoiding unnecessary recreation of resources.

- **Safety**: The confirmation step ensures you're aware of changes before they are applied.

In the next section, we'll dive into real-world scenarios and explore how to deploy a web application using Pulumi with Azure.

Stay tuned for more detailed content on working with real-world scenarios!