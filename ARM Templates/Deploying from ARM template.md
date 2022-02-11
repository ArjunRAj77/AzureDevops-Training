# ARM Templates -Azure Resource Manager Templates
<p>ARM templates are a form of infrastructure as code, a concept where you define the infrastructure you need to be deployed.
<br>You no longer need to click around the portal creating virtual machines or writing scripts to deploy a storage account.</p>

# Setting up ARm feature in VS Code
1. Open VS Code and Install Azure ARM Tool in VS Code.
2. Create a .json file for storing the template.
3. Type 'arm' in the code area and corresponding ARM templates will be visible. Choose the preffered template.
4. Fill the necessary fields and save.

# Deploying an ARM template in Azure
1. Open Azure Portal
2. Navigate to 'Deploy a custom templates' and click on Create.
3. Under ARM templates, copy the template from VS-Code.
4. Click on Create.
5. The Resource is now created as per the ARM Template.

# Deploying an ARM Template in Azure using Azure CLI
1. Open  Azure CLI
2. Upload the template on CLI
3. Creating a Storage Account using ARM templates can be done through the following code 
    ```
    New-AzResourceGroupDeployment -ResourceGroupName armrg -TemplateFile template.json
   ```
4. The resource is generated.   
