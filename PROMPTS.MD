

can you update this issue as ? 

Task: Scaffold and beautify index.html as Customize Github Copilot CLI  overview page with:

Title ""Customize Github Copilot CLI"
   - Copilot CLI works best when customized for your specific project and workflow.
   - Five navigation buttons linking to: 
   1- Custom Instructions - custominstructions.html
   2- Skills - skills.html
   3- Custom Agents - customagents.html
   4- MCP Servers - mcp.html
   5- Hooks - hooks.html

Assigned to: Github Copilot CLI 




can you update this issue as :

Task: Build a child page for Adding custom instructions for GitHub Copilot CLI

Title ""custom instructions for GitHub Copilot CLI"

   - Follow the same structure/style as the home page (index.html)
   - Use https://github.com/microsoftnorman/customize-your-repo-with-github-copilot for content 

Assigned to: Github Copilot CLI 

  Completion steps:

   1. Commit the changes
   2. git pull --rebase origin main
   3. git push origin main
   4. Close the issue via UI or gh issue close <number>


   update this issue as :

Task: Build a child page for Adding agent skills for GitHub Copilot CLI

Title "Adding agent skills for GitHub Copilot CLI"

   - Follow the same structure/style as the home page (index.html)
   - Use https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills for content 

Assigned to: Github Copilot CLI 

  Completion steps:

   1. Commit the changes
   2. git pull --rebase origin main
   3. git push origin main
   4. Close the issue via UI or gh issue close <number>




update this issue as :

Task: Build a child page for Creating and using custom agents for GitHub Copilot CLI

Title "Creating and using custom agents for GitHub Copilot CLI"

   - Follow the same structure/style as the home page (index.html)
   - Use https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/create-custom-agents-for-cli for content 

Assigned to: Github Copilot CLI 

  Completion steps:

   1. Commit the changes
   2. git pull --rebase origin main
   3. git push origin main
   4. Close the issue via UI or gh issue close <number>



Before issue 8 add another one titled "Azure Deployment" 

  Task: The application is deployed to Azure Container Apps with a CI/CD workflow (
  .github/workflows/azure-container-apps.yml).

   - ⚠️ The workflow only triggers on workflow_dispatch — not on push. Trigger manually with: gh 
  workflow run "Azure Container Apps CI/CD"
   - Confirm the Home Page, Primitives, and APE issues are closed
   - Verify the latest changes are live at the deployed URL
   - Re-trigger the workflow manually if needed

  Pre-flight requirement: Azure Container Apps Setup must be completed first (environment created,
  deployment secrets added).

  Assigned to: Copilot CLI

  Completion: Verify the live site is working, then close the issue.


  ● Issue 6 is titled "Clean Up Azure Resources" and is labeled post-demo.

  Task: After the demo is complete, delete all Azure resources to avoid unnecessary costs.

  Steps:

   1. Go to the Azure Portal
   2. Navigate to the Resource Group created for this demo
   3. Click Delete resource group and confirm
   4. Verify the Container App, Container Apps environment, Container Registry, and any associated 
  resources are fully removed


  An agent that will review Azure Container Apps from an Azure Well Architected Standppoint and      │
 │suggest improvements. Refer to https://github.com/MicrosoftDocs/well-architecte                    │
 │d/blob/main/well-architected/service-guides/azure-container-apps.md for full guideline but keep it │
 │simple short for the purpose of demo                                                               │
 │                                                                                                   │
 │                                         