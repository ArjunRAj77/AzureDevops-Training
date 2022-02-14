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
   
   1. Go to Azure Active Directory
   2. Go to users and add 4 users.
   3. Create dev group and add two users.(user1 and user2)
   4. Create prod group and add two users.(user2 and user4)
   5. Add contributor role for user 1 and user 3 and they can access all the resources
   
   <br>
   Test:
   
   1. login with user1 and user3 and check whether he can access every resource.
   2. login with user2 and user4 and check whether he can access any resource.
   
        
  

        
        
