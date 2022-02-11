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
            "name": "akhilvirtualNetwork1",
            "type": "Microsoft.Network/virtualNetworks",
            "apiVersion": "2020-11-01",
            "location": "East US 2",
            "tags": {
                "displayName": "virtualNetwork1"
            },
            "properties": {
                "addressSpace": {
                    "addressPrefixes": [
                        "10.4.0.0/16"
                    ]
                },
                "subnets": [
                    {
                        "name": "Subnet-1",
                        "properties": {
                            "addressPrefix": "10.4.1.0/24"
                        }
                    },
                    {
                        "name": "Subnet-2",
                        "properties": {
                            "addressPrefix": "10.4.2.0/24"
                        }
                    }
                ]
            }
         }
        ]
      }
     ```
  2. The Code for running it in Azure CLI is:
      ```
      New-AzResourceGroupDeployment -ResourceGroupName armrg -TemplateFile template.json
      ```
# Public IP ARM Template
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
            "name": "Akhilpublicip",
            "type": "Microsoft.Network/publicIPAddresses",
            "apiVersion": "2020-11-01",
            "location": "East US 2",
            "tags": {
                "displayName": "Akhilpublicip"
            },
            "properties": {
                "publicIPAllocationMethod": "Dynamic",
                "dnsSettings": {
                    "domainNameLabel": "dnsname1"
                  }
               }
            }
         ]
      }
     ```
   2. The Code for running it in Azure CLI is:
      ```
      New-AzResourceGroupDeployment -ResourceGroupName armrg -TemplateFile template.json
      ```
# Network Interface ARM Template
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
            "name": "networkinterface1-ustakhil",
            "type": "Microsoft.Network/networkInterfaces",
            "apiVersion": "2020-11-01",
            "location": "[resourceGroup().location]",
            "tags": {
                "displayName": "networkinterface1-ustakhil"
            },

            "properties": {
                "ipConfigurations": [
                    {
                        "name": "ipConfig1",
                        "properties": {
                            "privateIPAllocationMethod": "Dynamic",
                            "subnet": {
                                "id": "[resourceId('Microsoft.Network/virtualNetworks/subnets', 'UST-Akhil-Vnet', 'subnet1')]"
                            }
                        }
                    }
                ]
            }
          }
       ]
     }

     ```
  2. The Code for running it in Azure CLI is:
      ```
      New-AzResourceGroupDeployment -ResourceGroupName armrg -TemplateFile template.json
      ```
