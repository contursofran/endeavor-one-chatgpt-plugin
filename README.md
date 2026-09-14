# Endeavor One ChatGPT Plugin

Test distribution repository for the Endeavor One Sandbox ChatGPT plugin.

The plugin bundles:

- The registered `Endeavor One Sandbox` MCP app.
- Workflow instructions for safe Endeavor One searches and guarded meeting updates.

## Security

Installing this plugin does not grant access to Endeavor One or Salesforce. Each user must authenticate with an active Endeavor staff account. The MCP server enforces OAuth scopes, Salesforce staff identity, environment binding, record authorization, and explicit confirmation for supported writes.

This repository contains no Auth0 secrets, Salesforce credentials, bearer tokens, or Endeavor One application source code.

## Test locally

1. Clone this repository.
2. Open the repository as a workspace in the ChatGPT desktop app.
3. Restart the app if the `Endeavor One` repository marketplace does not appear.
4. Open **Plugins**, select the repository marketplace, and install `Endeavor One Sandbox`.
5. Connect your Endeavor staff account when prompted.

## Publish to an Enterprise workspace

A ChatGPT workspace admin can install the plugin locally, open its menu under **Plugins → Personal**, select **Publish**, and assign approved workspace roles. Workspace publication does not add the plugin to OpenAI's universal public directory.

See [OpenAI's plugin packaging and workspace publishing documentation](https://developers.openai.com/plugins/build/plugins).

## Environments

This repository currently distributes Sandbox only. Endeavor One Pre Prod must use a separate registered MCP app, Auth0 grant, plugin package, and workspace role assignment.

### Sandbox registration

The package references a registered ChatGPT app through `plugins/endeavor-one/.app.json`. The MCP endpoint and OAuth configuration live in that registration, not in this repository.

| Setting | Expected value |
| --- | --- |
| Registered app | `asdk_app_6aa814e1383881918b89895adac4f449` |
| MCP endpoint and OAuth audience | `https://mcp-sandbox-one-endeavor.vercel.app/api/mcp` |
| Auth0 issuer | `https://endeavor-one-mcp-sandbox.us.auth0.com/` |
| Salesforce | Sandbox FullCopy |

Version `0.1.1` replaces the legacy app reference. After updating the repository, refresh or reinstall the plugin from the repository marketplace and start a new chat. Workspace-published copies must also be updated by their owner; pushing this repository does not update an existing published copy automatically.

When connecting, verify that the login hostname is `endeavor-one-mcp-sandbox.us.auth0.com` and that only **Salesforce (sandbox)** is offered. A login on `dev-bbht8lnjhvupwysd.us.auth0.com` with both Salesforce options indicates an older registration is still being used.

Validate authentication separately from installation: complete Sandbox sign-in, then ask the plugin to get profile search options without creating or updating records. A successful package install alone does not prove authenticated MCP access.
