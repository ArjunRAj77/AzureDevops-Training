# Practical 3
# Aim
Use sonar cloud and complete code coverage of sample dot net code

# Procedure
 1. Create a new organization
 2. Go to organization setting and to policies
 3. Make the project public by 'Enable public project'
 4. Create a new public project.
 5. Go to sonarcloud.io and connect through azure devops and login with devops
 6. Provide org name and pat token for auth
 7. Go to project setting and select extensions and download sonarqube in extensions
 8. Create a service connection for sonarqube with the key provided.
 9. Select the free tier and select the public project
 10. Select ASP project and obtain credentials
 11. Upload sample code for ASP.net and create a yaml for pipeline
 
 ```
 trigger:
- main

pool: 'akhil-agent1'

variables: 
    solution: '**\*.sln' 
    buildplatform: 'Any CPU' 
    buildconfiguration: 'Release'

steps: 
- task: NuGetToolInstaller@0 
  displayName: 'Use NuGet 4.4.1' 
  inputs: 
    versionSpec: 4.4.1
          
- task: NuGetCommand@2 
  displayName: 'NuGet restore' 
  inputs: 
    restoreSolution: '**\*.sln'

- task: SonarSource.sonarcloud.14d9cde6-c1da-4d55-aa01-2965cd301255.SonarCloudPrepare@1
  displayName: 'Prepare analysis on SonarCloud'
  inputs:
    SonarCloud: 'sonarqube connection'
    organization: akhil0298
    projectKey: 'Akhil0298_Akhil-SonarPratical'
    projectName: 'Akhil-SonarPratical'

- task: VSBuild@1 
  displayName: 'Build solution' 
  inputs: 
    solution: '**\*.sln' 
    msbuildArgs: '/p:DeployOnBuild=true /p:WebPublishMethod=Package /p:PackageAsSingleFile=true /p:SkipInvalidConfigurations=true /p:PackageLocation="$(build.artifactstagingdirectory)\\"' 
    platform: '$(BuildPlatform)' 
    configuration: '$(BuildConfiguration)'

- task: SonarSource.sonarcloud.ce096e50-6155-4de8-8800-4221aaeed4a1.SonarCloudAnalyze@1
  displayName: 'Run Code Analysis'

- task: SonarSource.sonarcloud.38b27399-a642-40af-bb7d-9971f69712e8.SonarCloudPublish@1
  displayName: 'Publish Quality Gate Result'
  inputs:
    pollingTimeoutSec: 301

 ```
12. here in this yaml the task:`` SonarSource.sonarcloud.14d9cde6-c1da-4d55-aa01-2965cd301255.SonarCloudPrepare@1 ``needed to be changed with our configuration.
 <br> 1. For that go to pipelines and select classic pipeline with empty job
      <br>2. add a new job and search for prepare analysis on sonarcloud
          ![sonarcloud](https://user-images.githubusercontent.com/70442264/156499773-4e588f64-6bea-4276-ab52-98e460cad983.png)
      <br>3. Then click on view yaml
      <br>4. Copy from task and update the same in above yaml
      <br>5. Run pipeline using the yaml
      ![image](https://user-images.githubusercontent.com/23217592/156505817-c98898c4-d941-4e72-920d-a0b8db10fa3c.png)
      ![image](https://user-images.githubusercontent.com/23217592/156505965-1c9f522b-8c12-4f33-86ea-fce0ed496769.png)


 

