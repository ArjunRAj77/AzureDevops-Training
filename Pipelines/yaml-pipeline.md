# YAML pipelines 
<p>YAML is a human-readable data-serialization language. It is commonly used for configuration files and in applications where data is being stored or transmitted.</p> 
YAML is being used in easily create template for CI/CD integration.
<br>These are the list of demo pipelines created using YAML templates and its steps :

1. Pipeline with sample YAML template

# Pipeline with sample YAML template
1. Select ``` New Pipeline``` from Pipelines section
2. Select ``` Azure Repos Git ```  . 
3. Select a repository. 
4. Select ```existing Azure Pipeline YAML file ``` and select the YAML file
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
 6. The pipeline is up and running and created two seperate jobs based on the above YAML template.   
