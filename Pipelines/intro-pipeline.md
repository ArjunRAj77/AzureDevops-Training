Go to pipelines in Azure Devops Project
Click on new pipeline
click on use the classic editor
![1](https://user-images.githubusercontent.com/70442264/154905709-4f40aa45-551b-4a52-a0cc-c2d4b0236822.png)
give the repo details and click continue
select template as empty job.
Give a name and select your self hosted agent pool
![2](https://user-images.githubusercontent.com/70442264/154906095-da6b0bc4-d65c-4b96-bac9-e105bfd5055e.png)
click on add a task to agent job1
search for terraform and select install terraform
then search for terraform and select terraform
![3](https://user-images.githubusercontent.com/70442264/154906441-f814d530-b883-4677-ac13-8b7c9c01a3f8.png)
select first terraform and add configure subscription.
create a storage account in the resource group in azure portal and provide details there.
In the key section provide tf/terraform.tfstate as key
![4](https://user-images.githubusercontent.com/70442264/154906728-01f8650a-3056-4249-82bd-672e9a11e241.png)
select folder which contain the code for terraform.
Follow same steps for validate, plan and Apply

then click save and queue. Then run.
![5](https://user-images.githubusercontent.com/70442264/154907149-0b684c54-6251-45c3-9a9f-27aa92402265.png)
It will create a new resource group.



