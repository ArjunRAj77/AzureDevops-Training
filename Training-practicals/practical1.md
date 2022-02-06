# Practicals : 1

   # Objective

   1. Create 2 VM -'Windows server 2019' 
   2. Install IIS service in 2 VM
   3. Create index.html under dev folder in VM1
   4. Create index.html under prd folder in VM2
   5. Attach application gateway

   Note:
   1. First VM should display : "Dev Server" through index.html
   2. Second VM should display : "Prod Server" through index.html

   # Steps
        
   1. Create a VM with OS-' Windows Server 2019' and a new Vnet.
   ![vm1](https://user-images.githubusercontent.com/23217592/152671040-b1492e73-e44e-43ff-8046-8c9ced657645.jpg)
   2. Connect to VM using RDP and open server manager.
   3. Add a new Role from server Manager and install Web Server[IIS].
   ![iss installation](https://user-images.githubusercontent.com/23217592/152671044-1cf4bc86-61c1-4a19-b4ef-3be8bf0ccd61.jpg)
   4. In the wwwroot folder create a 'dev' folder and create a new index.html page with content: "Dev Server". 
   ![html](https://user-images.githubusercontent.com/23217592/152671056-eec6fd73-baaf-47dd-bd8d-512904910f0d.jpg)
   5.  Create a another VM using steps 1 to 3.
   6. In the wwwroot folder create a 'prd' folder and create a new index.html page with content: "Prod Server"
   7. 
        
        
        
