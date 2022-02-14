# Practicals : 1

   # Objective

   1. Create Private DNS server to communicate with internal Virtual network


   # Steps
        
   1. Create a Vnet 
   2. Create a private DNS zone
     ![1](https://user-images.githubusercontent.com/70442264/153826658-8e11433d-6aa8-43a8-8f00-8330efe48e6b.png)
   3. Go to Virtual Network Links and add        
      ![2](https://user-images.githubusercontent.com/70442264/153826877-ad0787d4-817a-4782-ab3a-62bd974496f6.png)
      ![3](https://user-images.githubusercontent.com/70442264/153827014-297a2a84-cf6d-430c-a014-c283d8ceb9a8.png)
        
   4. Create two Windows Vm.
   5. connect first vm using RDP
   6. Go to cmd and type ping vm2 name it will connect without private ip.
   7. connect to second vm using RDP
   8. Go to cmd and type ping vm1 name it will connect without private ip. 
   9. we create a Private DNS server and connected with Vnet to communicate internally.

  

        
        
