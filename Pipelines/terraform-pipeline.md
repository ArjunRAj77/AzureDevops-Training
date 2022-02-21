# Pipelines using Terraforms

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
  10. In Terraform validate and apply task : change Command to ``` validate and apply ``` add additional command argument : ``` --var-file=config.tfvars ```. <br>![tf9](https://user-images.githubusercontent.com/23217592/154908593-26157af1-a431-41cb-a463-3f7720056e4d.jpg)
  11. Select ``` save and queue```. Your pipeline is up and running.!<br>[tf10](https://user-images.githubusercontent.com/23217592/154908874-b6e006ff-0af0-403d-b4ca-6f86b4c78d04.jpg)
  12. The pipeline is successfully completed. ```CD is not activated in this pipeline. ``` <br> ![tf11](https://user-images.githubusercontent.com/23217592/154909093-e2dbd2cd-b5a5-4415-833c-556e8f3cfc72.jpg)





