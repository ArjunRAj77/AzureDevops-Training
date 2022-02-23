# Pipelines using Terraforms
  * The below pipelines are created using classic editor and as an empty job
  1. Pipeline for Creating an web app using Terraform
  2. Pipeline for creating a Resource Group Using Terraform
  3. Pipeline for creating a Storage Account Using Terraform

# 1 . Pipeline for Creating an web app using Terraform


  1. Upload terraform files in the Azure Git Repo <br>![tf1](https://user-images.githubusercontent.com/23217592/154906132-b29d294a-72b0-489c-9dc4-16e7765bd12d.jpg)
  2. Edit config.tg file and add the necessary data to the file.<br>![tf2](https://user-images.githubusercontent.com/23217592/154906328-3ba14d4a-6b70-471a-ad06-176f1515fafb.jpg)

  3. Go to 'Pipelines' and Click on 'New Pipeline'.<br> ![tf3](https://user-images.githubusercontent.com/23217592/154906639-30603788-16ab-4bc0-935b-6623e0c9ba17.jpg)

  4. Add agent pool name and Pipeline name. 
  5. Add tasks and search for 'terraform'. And add Terraform tool installer and Terraform.<br> ![tf5](https://user-images.githubusercontent.com/23217592/154907102-b37d1f4d-f1cf-4ba8-9860-dc7dffbf77bd.jpg)

  6. Terraform requires 4 steps : init, validate, plan ,validate and apply. Add tasks for these steps.<br> ![tf4](https://user-images.githubusercontent.com/23217592/154907452-125bcbc6-cc5e-40a0-9c09-ded042dabafc.jpg)

  7. In Terraform init task : change command to ```init``` , and add key as :``` tf/terraform.tfstate```. Also add other necessary subscription related details.<br> ![tf6](https://user-images.githubusercontent.com/23217592/154907856-81a1c81e-4b43-40f4-8784-ad8b0cdadc17.jpg)

  8. In Terraform validate task : change command to ```validate``` .<br> ![tf7](https://user-images.githubusercontent.com/23217592/154908093-785f9dc2-9f4b-46c7-b54d-61bd7c6151f0.jpg)
  9. In Terrform plan task: change Command to ``` Plan``` and add additional command argument : ``` --var-file=config.tfvars ```. <br> ![tf8](https://user-images.githubusercontent.com/23217592/154908385-b9e03090-c771-417d-af89-fee216e1e9ce.jpg)
  10. In Terraform validate and apply task : change Command to ``` validate and apply ``` .<br>Add additional command argument : ``` --var-file=config.tfvars ```. <br>![tf9](https://user-images.githubusercontent.com/23217592/154908593-26157af1-a431-41cb-a463-3f7720056e4d.jpg)
  11. Select ``` save and queue```. Your pipeline is up and running.!<br>
  ![tf10](https://user-images.githubusercontent.com/23217592/154908874-b6e006ff-0af0-403d-b4ca-6f86b4c78d04.jpg)
  13. The pipeline is successfully completed. ```CD is not activated in this pipeline. ``` <br> ![tf11](https://user-images.githubusercontent.com/23217592/154909093-e2dbd2cd-b5a5-4415-833c-556e8f3cfc72.jpg)

# 2 . Pipeline for creating a Resource Group Using Terraform

   1. Go to pipelines in Azure Devops Project
   2. Click on new pipeline
   3. Click on use the classic editor
      ![1](https://user-images.githubusercontent.com/70442264/154905709-4f40aa45-551b-4a52-a0cc-c2d4b0236822.png)
   4. Give the repo details and click continue
   5. Select template as empty job.
   6. Give a name and select your self hosted agent pool
      ![2](https://user-images.githubusercontent.com/70442264/154906095-da6b0bc4-d65c-4b96-bac9-e105bfd5055e.png)
   7. Click on add a task to agent job1
   8. Search for terraform and select install terraform
   9. Then search for terraform and select terraform
      ![3](https://user-images.githubusercontent.com/70442264/154906441-f814d530-b883-4677-ac13-8b7c9c01a3f8.png)
   10. Select first terraform and add configure subscription.
   11. Create a storage account in the resource group in azure portal and provide details there.
   12. In the key section provide tf/terraform.tfstate as key
      ![4](https://user-images.githubusercontent.com/70442264/154906728-01f8650a-3056-4249-82bd-672e9a11e241.png)
   13. Select folder which contain the code for terraform.
   14. Follow same steps for validate, plan and Apply
   15. Then click save and queue. Then run.
      ![5](https://user-images.githubusercontent.com/70442264/154907149-0b684c54-6251-45c3-9a9f-27aa92402265.png)
   16. It will create a new resource group.

# 3. Pipeline for creating a Storage Account Using Terraform
  1. Upload terraform files in the Azure Git Repo. <br>![tf1](https://user-images.githubusercontent.com/23217592/155058810-be460ea3-f376-4afa-8f8e-8cfd8cd6fb09.jpg)

  2. Edit config.tg file and add the necessary data to the file.<br>!![tf2](https://user-images.githubusercontent.com/23217592/155058832-e066b2f2-a212-4951-88b7-4310e07786ed.jpg)


  3. Go to 'Pipelines' and Click on 'New Pipeline'.<br> ![tf3](https://user-images.githubusercontent.com/23217592/154906639-30603788-16ab-4bc0-935b-6623e0c9ba17.jpg)

  4. Add Agent pool name and Pipeline name. 
  5. Add tasks and search for 'terraform'. And add Terraform tool installer and Terraform.<br> ![tf5](https://user-images.githubusercontent.com/23217592/154907102-b37d1f4d-f1cf-4ba8-9860-dc7dffbf77bd.jpg)

  6. Terraform requires 4 steps : init, validate, plan ,validate and apply. Add tasks for these steps.<br> ![tf4](https://user-images.githubusercontent.com/23217592/154907452-125bcbc6-cc5e-40a0-9c09-ded042dabafc.jpg)

  7. In Terraform init task : change command to ```init``` , and add key as :``` tf/terraform.tfstate```. Also add other necessary subscription related details.<br> ![tf6](https://user-images.githubusercontent.com/23217592/154907856-81a1c81e-4b43-40f4-8784-ad8b0cdadc17.jpg)

  8. In Terraform validate task : change command to ```validate``` .<br> ![tf7](https://user-images.githubusercontent.com/23217592/154908093-785f9dc2-9f4b-46c7-b54d-61bd7c6151f0.jpg)
  9. In Terrform plan task: change Command to ``` Plan``` and add additional command argument : ``` --var-file=config.tfvars ```. <br> ![tf8](https://user-images.githubusercontent.com/23217592/154908385-b9e03090-c771-417d-af89-fee216e1e9ce.jpg)
  10. In Terraform validate and apply task : change Command to ``` validate and apply ``` .<br>Add additional command argument : ``` --var-file=config.tfvars ```. <br>![tf9](https://user-images.githubusercontent.com/23217592/154908593-26157af1-a431-41cb-a463-3f7720056e4d.jpg)
  11. Select ``` save and queue```. Your pipeline is up and running.!<br>
  ![tf10](https://user-images.githubusercontent.com/23217592/154908874-b6e006ff-0af0-403d-b4ca-6f86b4c78d04.jpg)
  13. The pipeline is successfully completed. ```CD is not activated in this pipeline. ``` <br> ![tf11](https://user-images.githubusercontent.com/23217592/154909093-e2dbd2cd-b5a5-4415-833c-556e8f3cfc72.jpg)
  14. Storage account and resource group is created through this pipeline 

