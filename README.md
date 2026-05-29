# Customize GitHub Copilot CLI

A hands-on demo showcasing **GitHub Copilot CLI** building, deploying, and managing a mini web application — driven entirely by GitHub Issues and powered by Copilot CLI fleet mode.

---

## About This Demo

This demo walks through a realistic developer workflow driven entirely by GitHub Issues. Issues 2–7 can be assigned to Copilot CLI simultaneously via **fleet mode**, with each issue handled by a parallel subagent. Once all pages are built, an automated workflow triggers deployment to Azure.

By the end of the demo, a small web app has been:
- **Built** (home page + five child pages covering Copilot CLI customization topics)
- **Deployed** to Azure Container Apps via CI/CD

### Content Pages

| Page | Topic | Source |
|---|---|---|
| **Home** (`index.html`) | Customize GitHub Copilot CLI — overview with navigation to all child pages | — |
| **Custom Instructions** (`custominstructions.html`) | Adding custom instructions for Copilot CLI | [GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-custom-instructions) |
| **Skills** (`skills.html`) | Adding agent skills for Copilot CLI | [GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills) |
| **Custom Agents** (`customagents.html`) | Creating and using custom agents for Copilot CLI | [GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/create-custom-agents-for-cli) |
| **MCP Servers** (`mcp.html`) | Adding MCP servers for Copilot CLI | [GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-mcp-servers) |
| **Hooks** (`hooks.html`) | Adding hooks for Copilot CLI | [GitHub Docs](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-hooks) |

---

## Prerequisites

Before running this demo, make sure the following are in place:

- A GitHub repository with **9 issues** (see [Getting Started](#getting-started) below to create them)
- **GitHub Copilot** enabled on the account and the repository
- **Copilot CLI** installed and authenticated — verify with `gh auth status`

> 🎬 **The live demo starts at Issue 1.** All issues are worked through during the demo.

---

## Getting Started

After creating a new repo from this template, the **9 demo issues are not created automatically** — GitHub does not trigger workflows on the initial commit from a template.

Run this command once to seed all issues and labels:

```bash
gh workflow run "Setup Demo Issues" --repo <owner>/<your-new-repo>
```

After ~30 seconds, verify the issues were created:

```bash
gh issue list --repo <owner>/<your-new-repo>
```

> 💡 You can also trigger the workflow from the **Actions** tab → **Setup Demo Issues** → **Run workflow**.

---

## Demo Scenarios

### Issue 1 — Azure Container Apps Setup
**Label**: `init-demo`

Create Azure Container Registry and Container Apps resources, add deployment secrets, and verify the live URL. The deployment workflow is `workflow_dispatch` only — trigger it manually after setup to deploy the container.

---

### Issue 2 — Scaffold and Beautify the Home Page
**Label**: `copilot-cli`

Scaffold and beautify `index.html` as a **Customize GitHub Copilot CLI** overview page with five navigation buttons linking to the child pages (Custom Instructions, Skills, Custom Agents, MCP Servers, Hooks).

---

### Issue 3 — Custom Instructions Page
**Label**: `copilot-cli`

Build a child page for adding custom instructions for GitHub Copilot CLI. Follows the same structure and style as the home page.

---

### Issue 4 — Skills Page
**Label**: `copilot-cli`

Build a child page for adding agent skills for GitHub Copilot CLI. Follows the same structure and style as the home page.

---

### Issue 5 — Custom Agents Page
**Label**: `copilot-cli`

Build a child page for creating and using custom agents for GitHub Copilot CLI. Follows the same structure and style as the home page.

---

### Issue 6 — MCP Servers Page
**Label**: `copilot-cli`

Build a child page for adding MCP servers for GitHub Copilot CLI. Follows the same structure and style as the home page.

---

### Issue 7 — Hooks Page
**Label**: `copilot-cli`

Build a child page for adding hooks for GitHub Copilot CLI. Follows the same structure and style as the home page.

---

### Issue 8 — Azure Deployment
**Label**: `copilot-cli`

> **⚠️ Prerequisite**: Issues #2–#7 (all page issues) must be closed before deployment. Issue #1 (Azure Container Apps Setup) must be completed first.

Verify all page issues are closed, then trigger the deployment workflow. The `auto-deploy.yml` workflow can also trigger this automatically when the last page issue is closed.

---

### Issue 9 — Clean Up Azure Resources
**Label**: `post-demo`

After the demo is complete, delete all Azure resources (Resource Group, Container App, Container Registry) to avoid unnecessary costs.

---

## Fleet Mode & Auto-Deploy

Issues 2–7 can be assigned to Copilot CLI simultaneously via **fleet mode**. Each issue is handled by a parallel subagent, building all six pages concurrently.

The `auto-deploy.yml` workflow watches for issue closures. When all six page issues (2–7) are closed, it automatically triggers the Azure Container Apps CI/CD deployment — no manual intervention needed for Issue 8.

---

## Quick Reference

| Issue | Task | Label |
|---|---|---|
| 1 | Azure Container Apps Setup | `init-demo` |
| 2 | Scaffold & Beautify Home Page | `copilot-cli` |
| 3 | Custom Instructions Page | `copilot-cli` |
| 4 | Skills Page | `copilot-cli` |
| 5 | Custom Agents Page | `copilot-cli` |
| 6 | MCP Servers Page | `copilot-cli` |
| 7 | Hooks Page | `copilot-cli` |
| 8 | Azure Deployment | `copilot-cli` |
| 9 | Clean Up Azure Resources | `post-demo` |

---

## Repo Contents

| File | Description |
|---|---|
| `README.md` | This file |
| `Dockerfile` | Container image definition for Azure Container Apps deployment |
| `index.html` | Home page — Customize GitHub Copilot CLI overview |
| `custominstructions.html` | Child page — Custom Instructions |
| `skills.html` | Child page — Skills |
| `customagents.html` | Child page — Custom Agents |
| `mcp.html` | Child page — MCP Servers |
| `hooks.html` | Child page — Hooks |
| `template-azureapp.md` | Reusable runbook for Azure Container Apps setup (Issue #1) |
| `azure_resource.md` | Azure resource details (filled in during Issue #1) |
| `.github/workflows/setup-issues.yml` | Creates issues and labels — trigger manually after using the template (see [Getting Started](#getting-started)) |
| `.github/workflows/azure-container-apps.yml` | Manual-trigger deployment to Azure Container Apps |
| `.github/workflows/auto-deploy.yml` | Auto-triggers deployment when all page issues (2–7) are closed |
| `.github/agents/aca-infra-auditor.agent.md` | Custom agent for auditing Azure Container Apps deployments |
