Corporate Office VLAN Implementation

Separate departments into different VLANs while using the same physical switch.
This is how real companies isolate departments like HR, Finance, Admin and IT.

Device	one 2960 Switch	and four pc	

VLAN	Name
  10	HR
  20	Finance
  30	IT

Configure Switch

    enable
    configure terminal
    hostname Office-Switch
    no ip domain-lookup

Create VLANs

    vlan 10
    name HR
    exit
    
    vlan 20
    name Finance
    exit
    
    vlan 30
    name IT
    exit

Assign Ports

    HR
    interface fa0/1
    switchport mode access
    switchport access vlan 10
    exit
    
    Finance
    interface fa0/2
    switchport mode access
    switchport access vlan 20
    exit
    
    IT
    interface fa0/3
    switchport mode access
    switchport access vlan 30
    exit
    
    end
