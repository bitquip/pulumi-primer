# Multiple Stacks

### 5.1 Multiple Stacks

#### Why Use Multiple Stacks?

Using multiple stacks is crucial when you need to manage infrastructure across different environments, such as development, staging, and production. Each stack represents a specific environment and allows you to isolate and deploy resources independently.

#### Creating a New Stack

To create a new stack, use the following command:

```bash
pulumi stack init <stack-name>
```

For instance, to create a development stack:

```bash
pulumi stack init dev
```

#### Switching Between Stacks

You can easily switch between stacks using:

```bash
pulumi stack select <stack-name>
```

For example:

```bash
pulumi stack select dev
```

#### Benefits of Multiple Stacks

- **Isolation**: Each stack operates independently, reducing the risk of affecting other environments during changes or updates.

- **Configuration Management**: You can set different configuration values for each stack, tailoring them to specific environments.
