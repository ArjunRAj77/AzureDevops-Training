# Practicals : 3

   # Objective

   1. Create container based webapp using image rkudache31/djangowebnew


   # Steps
   1. Go to App Services 
   2. Create app service with 
        ->Publish: Docker Container![3](https://user-images.githubusercontent.com/70442264/152670951-daa07259-7d5a-4f8b-aaf5-b75fa7052c75.png)

   3. Create a new app plan    
![2](https://user-images.githubusercontent.com/70442264/152670877-d86c17cb-c6b9-4550-8081-cff25a94d14a.png)
   4. Click Docker
        1. Options: Single Container
        2. Image Source: Docker Hub
        3. Access Type: Public
        4. Image and Tag: specified container image( Here rkudache31/djangowebnew) 
   ![Uploading 3.png…]()
   5. Go to Resources
   6. Go to configurations ->Add New Application Settings
       1. ->Name: WEBSITES_PORT
       2. ->Value: 8000
   7. Go to URL
   8. Webpage is displayed
