# ARM Templates
The various ARM templates that are being used are the following:
<br>
1. Storage Account
2. Vnet
3. Network Interface
4. Public IP

# Storage Account ARM Template
 1. The template.json file is:
    ```
      {
      "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
       "contentVersion": "1.0.0.0",
       "parameters": {},
       "functions": [],
       "variables": {},
       "resources": [
             {
            "name": "ustakhilstorageaccount2",
            "type": "Microsoft.Storage/storageAccounts",
            "apiVersion": "2021-04-01",
            "tags": {
                "displayName": "ustakhilstorageaccount2"
            },
            "location": "[resourceGroup().location]",
            "kind": "StorageV2",
            "sku": {
                "name": "Standard_LRS"
            }
             }
           ]
        }
     ```
 2. The Code for running it in Azure CLI is:
    ```
    New-AzResourceGroupDeployment -ResourceGroupName armrg -TemplateFile template.json
    ```
# Vnet ARM Template
# Public Interface ARM Template
# Public IP ARM Template
