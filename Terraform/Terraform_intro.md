# Terraform
  Terraform is an open-source infrastructure as code software tool created by HashiCorp. Users define and provide data center infrastructure using a declarative configuration language known as HashiCorp Configuration Language, or optionally JSON.
 <br> Download Link : https://www.terraform.io/downloads 
 <br> Tutorial Link : https://learn.hashicorp.com/collections/terraform/azure-get-started?utm_source=terraform_io_download
 # Advantages
  1. Terraform can manage infrastructure on multiple cloud platforms.
  2. The human-readable configuration language helps you write infrastructure code quickly.
  3. Terraform's state allows you to track resource changes throughout your deployments.
  4. You can commit your configurations to version control to safely collaborate on infrastructure.
  
  # Installation Steps
  1. Download terrform from the above mentioned link
  2. Copy and paste it to a folder named 'Terraform' in your device
  3. Add the path of the variable to the system environment variables
  <br>Terraform is now installed into the device. It basically contains four action commands:
      1. init :  &emsp;  Prepare your working directory for other commands
      2. validate : &emsp; Check whether the configuration is valid
      3. plan : &emsp;   Show changes required by the current configuration
      4. apply :  &emsp;  Create or update infrastructure
      5. destroy : &emsp;  Destroy previously-created infrastructure
  <br>Terraform contains the extension .tf
  
  # Creating a resource group in Azure Using Terraform
  1. Open Visual Studio Code and create a folder.
  2. Create a file named 'main.tf'. Add the following codes to the file:
     ```
     provider "azurerm" {
     version = "~2.10.0"
     tenant_id = ""
     client_id = ""
     subscription_id = ""
     client_secret = ""
     features {}
  
     }
     resource "azurerm_resource_group" "example_name" {
     name ="example_name"
     location  = "West Europe"
  
     }
     ```
     Tenant ID,Client ID and Subscription ID can be provided from Azure Subscriptions.
     <br>Client_Secret can be obtained from Registered App from App Registry in Azure.(Create one if needed.)
   3. Type the following codes in terminal:
        ```
        terraform.exe init 
        terraform.exe plan 
        terraform.exe apply
        ```
      The Resource group is created in Azure.
  # Creating Subnet in Azure using Terraform commands
  
 
