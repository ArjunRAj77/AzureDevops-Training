# Practicals : 5

    # Objective

        1. Create NSG roll which replicate to all VM under that subnet


    # Steps
    Create a Linux Vm for testing NSG
    Create an NSG 
        ->Create an inbountrule to only allow 3389 port.
        

![9](https://user-images.githubusercontent.com/70442264/152723391-bd198063-85f2-40bb-8445-07b3333987b2.png)
    ->Go to subnet section, click associate and associate with VNet
    ![10](https://user-images.githubusercontent.com/70442264/152723559-719aacc9-fc05-4463-842b-6eb1709a53c0.png)
Test
    ->Open putty and try to connect VM. It will not connect.
