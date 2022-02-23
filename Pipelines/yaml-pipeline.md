# YAML pipelines 
<p>YAML is a human-readable data-serialization language. It is commonly used for configuration files and in applications where data is being stored or transmitted.</p> 
YAML is being used in easily create template for CI/CD integration.
<br>These are the list of demo pipelines created using YAML templates and its steps :

1. Pipeline with sample YAML template

# 1. Pipeline with sample YAML template
1. Select ``` New Pipeline``` from Pipelines section.
2. Select ``` Azure Repos Git ```  . 
   ![1](https://user-images.githubusercontent.com/23217592/155377878-cf35219e-f652-4ea9-b2b2-ba63ef1428e1.jpg)

3. Select a repository. 
   ![2](https://user-images.githubusercontent.com/23217592/155377912-c285e2be-6d90-44aa-b142-4140d9a1790d.jpg)

4. Select ```existing Azure Pipeline YAML file ``` and select the YAML file. 
   ![3](https://user-images.githubusercontent.com/23217592/155377938-5049f54d-c855-489f-a26d-ef5e0230db61.jpg)

5. Review and Run the Pipeline. The sample YAML file is :
```
name: sample-project
pool: 'mypool'
jobs:
- job: my_first_test_job_with_yaml
  timeoutInMinutes: 10
  steps:
  - powershell: write-host "Job Running"

- job: my_second_test_job_with_yaml
  steps: 
  - powershell: write-host "Job2 Running"
 ```

 6. The pipeline is up and running. It created two seperate jobs based on the above YAML template.   
    ![5](https://user-images.githubusercontent.com/23217592/155378038-1a0ce3c5-3623-404e-93f5-28ecebf9e33f.jpg)

# 2.
