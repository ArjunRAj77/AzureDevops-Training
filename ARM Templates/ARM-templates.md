# ARM Templates
The various ARM templates that are being used are the following:
<br>
1. Storage Account
2. Vnet
3. Network Interface
4. Public IP
5. V-net with Network Interface

# 1. Storage Account ARM Template
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
# 2. Vnet ARM Template
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
# 3. Public IP ARM Template
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
# 4. Network Interface ARM Template
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
 # 5. Vnet With Network Interface ARM Template
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
            "name": "ProdVnet",
            "type": "Microsoft.Network/virtualNetworks",
            "apiVersion": "2020-11-01",
            "location": "[resourceGroup().location]",
            "tags": {
                "displayName": "ProdVnet"
            },
            "properties": {
                "addressSpace": {
                    "addressPrefixes": [
                        "10.0.0.0/16"
                    ]
                },
                "subnets": [
                    {
                        "name": "Subnet-1",
                        "properties": {
                            "addressPrefix": "10.0.0.0/24"
                        }
                    },
                    {
                        "name": "Subnet-2",
                        "properties": {
                            "addressPrefix": "10.0.1.0/24"
                        }
                    }
                ]
            }
        },

        {
            "name": "networkInterface2-akhilust",
            "type": "Microsoft.Network/networkInterfaces",
            "apiVersion": "2020-11-01",
            "location": "[resourceGroup().location]",
            "tags": {
                "displayName": "networkInterface2-akhilust"
            },
            "dependsOn": [
                "[resourceId('Microsoft.Network/virtualNetworks', 'ProdVnet')]"
            ],
            "properties": {
                "ipConfigurations": [
                    {
                        "name": "ipConfig1",
                        "properties": {
                            "privateIPAllocationMethod": "Dynamic",
                            "subnet": {
                                "id": "[resourceId('Microsoft.Network/virtualNetworks/subnets', 'ProdVnet', 'Subnet-1')]"
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
 # 6. VM-Windows
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
            "name": "[toLower('storageaccustakhil2')]",
            "type": "Microsoft.Storage/storageAccounts",
            "apiVersion": "2021-04-01",
            "location": "East US",
            "tags": {
                "displayName": "akhilwinmachine Storage Account"
            },
            "sku": {
                "name": "Standard_LRS"
            },
            "kind": "Storage"
        },
        {
            "name": "akhilvm1-publicIp",
            "type": "Microsoft.Network/publicIPAddresses",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "tags": {
                "displayName": "PublicIPAddress"
            },
            "properties": {
                "publicIPAllocationMethod": "Dynamic",
                "dnsSettings": {
                    "domainNameLabel": "[toLower('akhilwinmachine')]"
                }
            }
        },
        {
            "name": "akhilvm1nsg",
            "type": "Microsoft.Network/networkSecurityGroups",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "properties": {
                "securityRules": [
                    {
                        "name": "nsgRule1",
                        "properties": {
                            "description": "description",
                            "protocol": "Tcp",
                            "sourcePortRange": "*",
                            "destinationPortRange": "3389",
                            "sourceAddressPrefix": "*",
                            "destinationAddressPrefix": "*",
                            "access": "Allow",
                            "priority": 100,
                            "direction": "Inbound"
                        }
                    }
                ]
            }
        },
        {
            "name": "akhilvm1vnet",
            "type": "Microsoft.Network/virtualNetworks",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "dependsOn": [
                "[resourceId('Microsoft.Network/networkSecurityGroups', 'akhilvm1nsg')]"
            ],
            "tags": {
                "displayName": "akhilvm1vnet"
            },
            "properties": {
                "addressSpace": {
                    "addressPrefixes": [
                        "10.0.0.0/16"
                    ]
                },
                "subnets": [
                    {
                        "name": "akhilvm1vnet-Subnet",
                        "properties": {
                            "addressPrefix": "10.0.0.0/24",
                            "networkSecurityGroup": {
                                "id": "[resourceId('Microsoft.Network/networkSecurityGroups', 'akhilvm1nsg')]"
                            }
                        }
                    }
                ]
            }
        },
        {
            "name": "akhilvm1networkinterface",
            "type": "Microsoft.Network/networkInterfaces",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "dependsOn": [
                "[resourceId('Microsoft.Network/publicIPAddresses', 'akhilvm1-publicIp')]",
                "[resourceId('Microsoft.Network/virtualNetworks', 'akhilvm1vnet')]"
            ],
            "tags": {
                "displayName": "akhilwinmachine Network Interface"
            },
            "properties": {
                "ipConfigurations": [
                    {
                        "name": "ipConfig1",
                        "properties": {
                            "privateIPAllocationMethod": "Dynamic",
                            "publicIPAddress": {
                                "id": "[resourceId('Microsoft.Network/publicIPAddresses', 'akhilvm1-publicIp')]"
                            },
                            "subnet": {
                                "id": "[resourceId('Microsoft.Network/virtualNetworks/subnets', 'akhilvm1vnet', 'akhilvm1vnet-Subnet')]"
                            }
                        }
                    }
                ]
            }
        },
        {
            "name": "akhilwinmachine",
            "type": "Microsoft.Compute/virtualMachines",
            "apiVersion": "2021-03-01",
            "location": "East US",
            "dependsOn": [
                "[resourceId('Microsoft.Storage/storageAccounts', toLower('storageaccustakhil2'))]",
                "[resourceId('Microsoft.Network/networkInterfaces', 'akhilvm1networkinterface')]"
            ],
            "tags": {
                "displayName": "akhilwinmachine"
            },
            "properties": {
                "hardwareProfile": {
                    "vmSize": "Standard_A2_v2"
                },
                "osProfile": {
                    "computerName": "akhilwinmachine",
                    "adminUsername": "akhilanil",
                    "adminPassword": "Akhilmanil@123"
                },
                "storageProfile": {
                    "imageReference": {
                        "publisher": "MicrosoftWindowsServer",
                        "offer": "WindowsServer",
                        "sku": "2012-R2-Datacenter",
                        "version": "latest"
                    },
                    "osDisk": {
                        "name": "akhilwinmachineOSDisk",
                        "caching": "ReadWrite",
                        "createOption": "FromImage"
                    }
                },
                "networkProfile": {
                    "networkInterfaces": [
                        {
                            "id": "[resourceId('Microsoft.Network/networkInterfaces', 'akhilvm1networkinterface')]"
                        }
                    ]
                },
                "diagnosticsProfile": {
                    "bootDiagnostics": {
                        "enabled": true,
                        "storageUri": "[reference(resourceId('Microsoft.Storage/storageAccounts/', toLower('storageaccustakhil2'))).primaryEndpoints.blob]"
                    }
                }
            }
        }
    ],
    "outputs": {}
}
```
     2. The Code for running it in Azure CLI is:
      ```
      New-AzResourceGroupDeployment -ResourceGroupName armrg -TemplateFile template.json
      ```
      
 # 7. VM-Windows with password passed as parameter through KeyVault
   1. The template.json file is:
   ```
   {
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "vmpass":{
            "type": "securestring"
        }
    },
    "functions": [],
    "variables": {},
    "resources": [
        {
            "name": "[toLower('storageaccustakhil2')]",
            "type": "Microsoft.Storage/storageAccounts",
            "apiVersion": "2021-04-01",
            "location": "East US",
            "tags": {
                "displayName": "akhilwinmachine Storage Account"
            },
            "sku": {
                "name": "Standard_LRS"
            },
            "kind": "Storage"
        },
        {
            "name": "akhilvm1-publicIp",
            "type": "Microsoft.Network/publicIPAddresses",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "tags": {
                "displayName": "PublicIPAddress"
            },
            "properties": {
                "publicIPAllocationMethod": "Dynamic",
                "dnsSettings": {
                    "domainNameLabel": "[toLower('akhilwinmachine')]"
                }
            }
        },
        {
            "name": "akhilvm1nsg",
            "type": "Microsoft.Network/networkSecurityGroups",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "properties": {
                "securityRules": [
                    {
                        "name": "nsgRule1",
                        "properties": {
                            "description": "description",
                            "protocol": "Tcp",
                            "sourcePortRange": "*",
                            "destinationPortRange": "3389",
                            "sourceAddressPrefix": "*",
                            "destinationAddressPrefix": "*",
                            "access": "Allow",
                            "priority": 100,
                            "direction": "Inbound"
                        }
                    }
                ]
            }
        },
        {
            "name": "akhilvm1vnet",
            "type": "Microsoft.Network/virtualNetworks",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "dependsOn": [
                "[resourceId('Microsoft.Network/networkSecurityGroups', 'akhilvm1nsg')]"
            ],
            "tags": {
                "displayName": "akhilvm1vnet"
            },
            "properties": {
                "addressSpace": {
                    "addressPrefixes": [
                        "10.0.0.0/16"
                    ]
                },
                "subnets": [
                    {
                        "name": "akhilvm1vnet-Subnet",
                        "properties": {
                            "addressPrefix": "10.0.0.0/24",
                            "networkSecurityGroup": {
                                "id": "[resourceId('Microsoft.Network/networkSecurityGroups', 'akhilvm1nsg')]"
                            }
                        }
                    }
                ]
            }
        },
        {
            "name": "akhilvm1networkinterface",
            "type": "Microsoft.Network/networkInterfaces",
            "apiVersion": "2020-11-01",
            "location": "East US",
            "dependsOn": [
                "[resourceId('Microsoft.Network/publicIPAddresses', 'akhilvm1-publicIp')]",
                "[resourceId('Microsoft.Network/virtualNetworks', 'akhilvm1vnet')]"
            ],
            "tags": {
                "displayName": "akhilwinmachine Network Interface"
            },
            "properties": {
                "ipConfigurations": [
                    {
                        "name": "ipConfig1",
                        "properties": {
                            "privateIPAllocationMethod": "Dynamic",
                            "publicIPAddress": {
                                "id": "[resourceId('Microsoft.Network/publicIPAddresses', 'akhilvm1-publicIp')]"
                            },
                            "subnet": {
                                "id": "[resourceId('Microsoft.Network/virtualNetworks/subnets', 'akhilvm1vnet', 'akhilvm1vnet-Subnet')]"
                            }
                        }
                    }
                ]
            }
        },
        {
            "name": "akhilwinmachine",
            "type": "Microsoft.Compute/virtualMachines",
            "apiVersion": "2021-03-01",
            "location": "East US",
            "dependsOn": [
                "[resourceId('Microsoft.Storage/storageAccounts', toLower('storageaccustakhil2'))]",
                "[resourceId('Microsoft.Network/networkInterfaces', 'akhilvm1networkinterface')]"
            ],
            "tags": {
                "displayName": "akhilwinmachine"
            },
            "properties": {
                "hardwareProfile": {
                    "vmSize": "Standard_A2_v2"
                },
                "osProfile": {
                    "computerName": "akhilwinmachine",
                    "adminUsername": "akhilanil",
                    "adminPassword": "[parameters('vmpass')]"
                },
                "storageProfile": {
                    "imageReference": {
                        "publisher": "MicrosoftWindowsServer",
                        "offer": "WindowsServer",
                        "sku": "2012-R2-Datacenter",
                        "version": "latest"
                    },
                    "osDisk": {
                        "name": "akhilwinmachineOSDisk",
                        "caching": "ReadWrite",
                        "createOption": "FromImage"
                    }
                },
                "networkProfile": {
                    "networkInterfaces": [
                        {
                            "id": "[resourceId('Microsoft.Network/networkInterfaces', 'akhilvm1networkinterface')]"
                        }
                    ]
                },
                "diagnosticsProfile": {
                    "bootDiagnostics": {
                        "enabled": true,
                        "storageUri": "[reference(resourceId('Microsoft.Storage/storageAccounts/', toLower('storageaccustakhil2'))).primaryEndpoints.blob]"
                    }
                }
            }
        }
    ],
    "outputs": {}
}
```
2. The parameters.json file is
```
{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "vmpass": {
            "reference":{
                "keyVault": {
                    "id":"/subscriptions/725a1599-e04c-4699-84ff-c83ea6687708/resourceGroups/akhilstg/providers/Microsoft.KeyVault/vaults/ust-akhil-keyvault"

                },
                "secretName": "vmpass"
            } 
        }
    }
}
```
# Steps
 Create a Key Vault and Add a secret with upload option manual, name and value as vm password
 Go to properties and copy resource id and paste in the id in parameter file
 Add name of secret which created in key vault in parameter.json file
 Add this parameter in {parameter} in the main json template file and update password for vm with [parameters('vmpass')].
 
 ```
 3. The Code for running it in Azure CLI is:
      ```
      New-AzResourceGroupDeployment -ResourceGroupName armrg -TemplateFile template.json -TemplateParameterFile .\filename.parameters.json
 
