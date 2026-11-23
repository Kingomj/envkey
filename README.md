# envkey

API keys and environment variables need to reach the right applications without ending up in source control or scattered configuration files. envkey manages application configuration with end-to-end encryption and loads it into the processes that need it.

## Features

- Encrypt API keys and other configuration secrets end to end with NaCl.
- Manage environment variables and access permissions for applications, environments, people, and devices.
- Track configuration changes with version history and audit logs.
- Share configuration through reusable blocks and environment inheritance.
- Load environment variables into commands with the cross-platform `envkey-source` tool.
- Reload environment variables when configuration changes, with support determined by the integration in use.

## Installation

From a local checkout of this TypeScript project, install its dependencies:

```bash
npm install
```

This installs project dependencies; it does not install or configure the desktop application or integration tools. For the upstream installation procedure, see the [envkey-source documentation](https://docs-v2.envkey.com/docs/envkey-source). Treat those instructions as upstream reference material, not release instructions for this standalone project.

**Cloud availability:** The upstream project announced that EnvKey Cloud would shut down on February 1, 2025. Do not rely on its former hosted registration flow when setting up a deployment.

## Usage

Once `envkey-source` is installed and configured for an application and environment, run your application's command through it:

```bash
envkey-source -- npm start
```

The command after `--` runs with the environment variables supplied by EnvKey. In this example, `npm start` runs the start script defined in your application's `package.json`.

You can use the same integration with other shell commands:

```bash
envkey-source -- node app.js
```

See the upstream [integration quickstart](https://docs-v2.envkey.com/docs/integration-quickstart) for configuration details. Language-specific integrations are also available upstream for Node.js, Python, Go, Ruby, and PHP.

## License

MIT. This standalone project is based on [envkey/envkey](https://github.com/envkey/envkey), which is released under the MIT License. Retain the upstream copyright and permission notices in copies or substantial portions of the software. Upstream commercial server-side extensions are separately licensed and are not covered by that MIT grant.

