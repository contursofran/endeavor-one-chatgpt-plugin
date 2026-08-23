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
