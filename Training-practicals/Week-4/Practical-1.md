# Practical 1 
# Aim
Use Dotnet sample code and create build using classic editor and yaml
 
 <br>Dotnet Sample Code : [dotnet sample project](https://github.com/ArjunRAj77/AzureDevops-Training/blob/main/Code%20samples/dotnetsimpleproject-master.zip)
  
# Procedure

# 1. Creating build Using YAML
 1. Upload the .net code into the Azure repo. 
     <br>![image](https://user-images.githubusercontent.com/23217592/156424065-45ac33f9-02b1-4bdf-ae4d-89e62772c9f1.png)
 
 2. Configure the yaml file ``` azure-pipelines.yaml``` with the agent pool name and trigger mechanism.
     ![image](https://user-images.githubusercontent.com/23217592/156424305-73df8688-404c-4732-9499-bdbe36d392e0.png)

 4. Run the pipeline. The .net code solution is executed. 
    ![image](https://user-images.githubusercontent.com/23217592/156424223-ffe7f3d9-0edf-44ac-85f0-6d7874c395cd.png)

# 2. Creating build Using Classic Editor
  1. Open Classic Editor from Pipeline.
  2. Select .ASP.Net project template
  4. Select the solution path 
     <br>![image](https://user-images.githubusercontent.com/23217592/156498065-47edb28e-e0f5-403a-b3e6-9ce68b10ad0c.png)
  6. The pipeline is executed successfully
      ![image](https://user-images.githubusercontent.com/23217592/156498107-290a647a-a150-4d0a-b3f1-276a8d38bd57.png)



