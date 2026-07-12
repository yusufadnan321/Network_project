Design a network system between two branceh office and connected 

use two 2911 router for each one office, two 2960 switch and two pc each office

IP Plan
  Branch A LAN
    Device	IP
    R1 G0/0	192.168.1.1
    PC1	192.168.1.10
   
  Branch B LAN
    Device	IP  
    R2 G0/1	192.168.2.1
    PC2	192.168.2.10  
  Router-to-Router Link
    Device	IP
    R1 G0/1	10.0.0.1
    R2 G0/0	10.0.0.2

Configure Router 1

    enable
    configure terminal
    
    hostname BranchA
    
    interface g0/0
    ip address 192.168.1.1 255.255.255.0
    no shutdown
    exit
    
    interface s0/0/0
    ip address 10.0.0.1 255.255.255.252
    no shutdown
    exit
    
    ip route 192.168.2.0 255.255.255.0 10.0.0.2
    
    end

Configure Router 2

    enable
    configure terminal
    
    hostname BranchB
    
    interface g0/0
    ip address 192.168.2.1 255.255.255.0
    no shutdown
    exit
    
    interface s0/0/0
    ip address 10.0.0.2 255.255.255.252
    no shutdown
    exit
    
    ip route 192.168.1.0 255.255.255.0 10.0.0.1
    
    end



