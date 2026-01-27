# WRK493 TechConnect 2026 Declarative Agents

This project contains two Microsoft 365 Copilot declarative agents built with Microsoft 365 Agents Toolkit for the WRK493 TechConnect 2026 session. It includes separate manifests, instructions, and plugin definitions for Act 1 and Act 2.

## What’s in this repo

### Act 1 — WRK493 TechConnect 2026
General-purpose declarative agent grounded in:
- OneDrive/SharePoint content
- Teams messages
- People and Email
- Graph connectors
- Code Interpreter and Graphic Art

### Act 2 — Client Meeting Analyst
Specialized agent that connects to Salesforce data through:
- OpenAPI plugin (SOQL query endpoint)
- MCP server plugin for meeting/product insights

Includes curated conversation starters and a non-production disclaimer.

## Prerequisites

- [Node.js](https://nodejs.org/) 18, 20, or 22
- A [Microsoft 365 developer account](https://docs.microsoft.com/microsoftteams/platform/toolkit/accounts)
- Microsoft 365 Agents Toolkit (VS Code extension or CLI)
- A Microsoft 365 Copilot license

## Run locally

1. In VS Code, open the Microsoft 365 Agents Toolkit view.
2. Sign in with your Microsoft 365 account if prompted.
3. Use the launch configuration to preview locally in Copilot (Edge or Chrome).
4. In Copilot, pick the agent you want (Act 1 or Act 2).

## Provisioning and packaging

The project defines two provisioning flows:
- Act 1 + Act 2 combined provisioning in [m365agents.yml](m365agents.yml)
- Single-app local provisioning in [m365agents.local.yml](m365agents.local.yml)

App packages are built to appPackage/build for each environment.

## Key files

| Path | Description |
| --- | --- |
| [m365agents.yml](m365agents.yml) | Main project configuration; provisions and packages Act 1 and Act 2. |
| [m365agents.local.yml](m365agents.local.yml) | Local-only provisioning for a single app. |
| [appPackage/manifest_Act1.json](appPackage/manifest_Act1.json) | Teams app manifest for Act 1. |
| [appPackage/manifest_Act2.json](appPackage/manifest_Act2.json) | Teams app manifest for Act 2. |
| [appPackage/declarativeAgent_Act1.json](appPackage/declarativeAgent_Act1.json) | Agent definition, grounding sources, and capabilities for Act 1. |
| [appPackage/declarativeAgent_Act2.json](appPackage/declarativeAgent_Act2.json) | Agent definition, actions, and starters for Act 2. |
| [appPackage/instruction_Act1.txt](appPackage/instruction_Act1.txt) | System instructions for Act 1. |
| [appPackage/instruction_Act2.txt](appPackage/instruction_Act2.txt) | System instructions for Act 2. |
| [appPackage/mcp-plugin.json](appPackage/mcp-plugin.json) | MCP plugin for meeting sentiment, product trends, and insights. |
| [appPackage/sf-plugin.json](appPackage/sf-plugin.json) | OpenAPI plugin for Salesforce SOQL queries. |
| [appPackage/apiSpecificationFile/openapi.yaml](appPackage/apiSpecificationFile/openapi.yaml) | OpenAPI spec for Salesforce query endpoint. |

## Notes and disclaimers

The Act 2 agent includes a non‑production disclaimer and is intended for demonstration only. Outputs are AI‑generated and may be incomplete or inaccurate.

## References

- [Declarative agents for Microsoft 365](https://aka.ms/teams-toolkit-declarative-agent)
