---
name: "Issue 8 — Azure Deployment"
about: "Verify and trigger deployment after all pages are built"
title: "Azure Deployment"
labels: "copilot-cli"
---

## Task
The application is deployed to Azure Container Apps and a CI/CD workflow is in place (`.github/workflows/azure-container-apps.yml`).

> ⚠️ **Important**: The workflow only triggers on `workflow_dispatch` — **not on push**. Trigger manually with:
> ```bash
> gh workflow run "Azure Container Apps CI/CD"
> ```

For this step:
1. Confirm the **Home Page**, **Custom Instructions**, **Skills**, **Custom Agents**, **MCP Servers**, and **Hooks** issues are closed
2. Verify the latest changes are live at the deployed URL
3. If anything needs to be re-triggered, trigger the workflow manually using the command above

## Pre-flight requirement
The **Azure Container Apps Setup** issue must be completed first (environment created, deployment secrets added).

## Assigned to
GitHub Copilot CLI

## Completion
Once deployment is verified and the live site is confirmed working, close this issue from the GitHub UI or with `gh issue close <this-issue-number>`.
