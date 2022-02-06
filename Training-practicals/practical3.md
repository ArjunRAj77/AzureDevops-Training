# Practicals : 3

    # Objective

        1. Create container based webapp using image rkudache31/djangowebnew


    # Steps
    Go to app services 
    Create app service with 
        ->Publish: Docker Container![3](https://user-images.githubusercontent.com/70442264/152670951-daa07259-7d5a-4f8b-aaf5-b75fa7052c75.png)

        ->Create a new app plan
        
![2](https://user-images.githubusercontent.com/70442264/152670877-d86c17cb-c6b9-4550-8081-cff25a94d14a.png)
    Click Docker
    ->Options: Single Container
    ->Image Source: Docker Hub
    ->Access Type: Public
    ->Image and Tag: specified container image( Here rkudache31/djangowebnew)
    
    ![Uploading 3.png…]()
Go to Resources
Go to configurations
    ->Add New Application Settings
        ->Name: WEBSITES_PORT
        ->Value: 8000
Go to URL
You see the webpage
