Instead of manually assigning IP addresses, configure the router as a DHCP Server so PCs automatically receive their IP configuration.

Use one 2911 router, one 2960 switch and four pc 

Router Ip and defualt gateway - 192.168.50.1

DHCP range - 192.168.50.10 - 192.168.50.254

Ip range 192.168.50.1 to 192.168.50.9 are reserved becuase can assign to directly to when its needed 

Configure Router 

      enable
      configure terminal
      
      hostname DHCP-Router
      
      no ip domain-lookup
      
      interface g0/0
      ip address 192.168.50.1 255.255.255.0
      no shutdown
      exit
      
      ip dhcp excluded-address 192.168.50.1 192.168.50.9

      ip dhcp pool OFFICE

      network 192.168.50.0 255.255.255.0
    
      default-router 192.168.50.1
    
      dns-server 8.8.8.8
    
      exit
