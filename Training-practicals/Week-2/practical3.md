# Practicals : 3

   # Objective

   1. Create user and assign Dev group and prod group
         <br>user1 - dev
         <br>user2 - dev
         <br>user3 - prod
         <br>user4 - prod
         <br>and provide role so they can create resource under that related group you have to define such role this user can ale to create resource on that froup only
   <br>e:g user1 -> devrg-> create any resource
       <br>user3 -> prodrg -> create any resource


   # Steps
   
   Go to Azure Active Directory
   Go to users and add 4 users.
   Create 2 resource group as 1: dev and 2: prod
   Go to dev resource group and go to Access Control(IAM)
   add role assignment and select members as user1 and user2
   Go to prod resource group and go to Access Control(IAM)
   add role assignment and select members as user3 and user4.
   
   Test:
      login with user1 or user2 and check whether he can access anyother resource other than prod.
      login with user3 or user4 and check whether he can access anyother resource other than prod.
      
        
  

        
        
