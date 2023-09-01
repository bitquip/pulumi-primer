# Configuration and Secrets

### 5.2 Configuration and Secrets

#### Configuration Values

Pulumi allows you to configure your infrastructure with variables. This flexibility is handy when you need to adapt your code for various environments.

To set a configuration value:

```bash
pulumi config set <key> <value>
```

For example:

```bash
pulumi config set vmCount 3
```

In your code, you can access these values like this:

```typescript
const vmCount = pulumi.config.getNumber("vmCount") || 1; // Default to 1 if not set
```

#### Secrets

Pulumi also provides a secure way to store secrets, such as database passwords, using its secret mechanism:

```bash
pulumi config set --secret dbPassword SecretPassword123
```

In your code, retrieve secrets like this:

```typescript
const dbPassword = pulumi.secret(pulumi.config.require("dbPassword"));
```

#### Benefits of Configuration Management

- **Environment Flexibility**: Configuration values make it easy to adapt your code for different environments without modifying the code itself.

- **Security**: Storing secrets securely ensures sensitive information is protected.
