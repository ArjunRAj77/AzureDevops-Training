# Practicals : 4

    # Objective

        1. Create 2 VM on different Vnet
        2. Communicate Both Vm with each other



    # Steps
    Create 2 Windows VMs in 2 different Vnets.
    Install ISS services in the 2 VMs. 
        #SelfTest
            ->Use public IP to test we successfully install web server
            -> RDP VM1
            ->Open explorer and try to connect VM2 webserver using privateip ( Will note load)
    Open VNet1
    Go to peering and add 
    

![1](https://user-images.githubusercontent.com/70442264/152670582-69e8bef8-563f-4824-b396-e4eec08be680.png)
    It will automatically add peering in Vnet2 as well.
    Now go to VM1 and try to connect VM2 webserver using private ip. It will load.
    
    
