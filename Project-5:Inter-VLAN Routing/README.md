Inter-VLAN Routing

User one 2911 router, one 2960 switch and four pc

VLAN Plan
  | VLAN | Name    | Network         |
  | ---- | ------- | --------------- |
  | 10   | HR      | 192.168.10.0/24 |
  | 20   | IT      | 192.168.20.0/24 |
  | 30   | AC      | 192.168.30.0/24 |
  | 40   | ADMIN   | 192.168.40.0/24 |

IP Plan
  Router G0/0.10	192.168.10.1
  Router G0/0.20	192.168.20.1
  Router G0/0.30	192.168.30.1
  Router G0/0.40	192.168.40.1
  PC1	192.168.10.10
  PC2	192.168.20.10
  PC3	192.168.30.10
  PC4	192.168.40.10

Configure the Switch
  Create VLANs
  
      enable
      configure terminal
      hostname office-switch
      
      vlan 10
      name HR
      exit
      vlan 20
      name IT
      exit
      vlan 30
      name AC
      exit
      vlan 40
      name ADMIN
      exit

  Assign Ports
  
    interface fa0/1
    switchport mode access
    switchport access vlan 10
    exit
    interface fa0/2
    switchport mode access
    switchport access vlan 20
    exit
    interface fa0/3
    switchport mode access
    switchport access vlan 30
    exit
    
    interface fa0/4
    switchport mode access
    switchport access vlan 40
    exit

  Configure the Trunk Port
    
    interface f0/5
    switchport mode trunk
    exit

  Configure the Router

    enable
    configure terminal
    hostname office-router
    interface g0/0
    no shutdown
    exit

  Subinterface

    interface g0/0.10
    encapsulation dot1Q 10
    ip address 192.168.10.1 255.255.255.0
    exit
    interface g0/0.20
    encapsulation dot1Q 20
    ip address 192.168.20.1 255.255.255.0
    exit
    interface g0/0.30
    encapsulation dot1Q 30
    ip address 192.168.30.1 255.255.255.0
    exit
    interface g0/0.40
    encapsulation dot1Q 40
    ip address 192.168.40.1 255.255.255.0
    exit

    end
