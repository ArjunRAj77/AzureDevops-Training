# Practicals : 2

   # Objective

   1. Create 2 VM 
   2. Attach standard Load Balancer

   # Steps
   1. Create 2 linux VMs in same VNet and install apache services in two VMs (apt-get install apache2;<h-1>Processing VM1</h-1>)
   2. Add inboundport rule to open port 80
   3. Check both VM apache server is up and running.
   4. Create a Loadbalancer 
   ![4](https://user-images.githubusercontent.com/70442264/152671639-24976645-9fea-45c0-9b64-d575074546e1.png) 
   5. In Frontend IP configuration,Add frontend IP configuration     
   ![5](https://user-images.githubusercontent.com/70442264/152671694-a63ec3ca-2af2-437e-bcc9-63c368f444b5.png)
   6. In backendpool,Create 2 backendpool for VM1 and VM2       
   ![6](https://user-images.githubusercontent.com/70442264/152671714-fd8f0613-f4ed-45bf-979a-f43227e7272b.png)
   7. In Inboundrule:->Load Balancing rule   
   ![7](https://user-images.githubusercontent.com/70442264/152673853-11932530-dc22-4c41-970a-066836cf9eb5.png)
   8. In outbound rule:
   ![8](https://user-images.githubusercontent.com/70442264/152673869-530d35a4-3b57-45e3-ae0e-6a349a7cb502.png)
   9. Now Create a Load Balancer
   10. Use public ip of Load Balancer to view apache server
        
