Create a small office wireless network with WPA2 security where laptops obtain IP addresses automatically using DHCP.


Device       	Quantity
Router 2911    	1
Switch 2960	    1
Access Point	  1
Laptop	        2

| Device    | IP                               |
| --------- | -------------------------------- |
| Router    | 192.168.100.1                    |
| DHCP Pool | 192.168.100.10 - 192.168.100.254 |

Configure Router

    enable
    configure terminal
    hostname Wireless-Router
    no ip domain-lookup
    interface g0/0
    ip address 192.168.100.1 255.255.255.0
    no shutdown
    exit

Configure DHCP

    ip dhcp excluded-address 192.168.100.1 192.168.100.9
    ip dhcp pool WIFI
    network 192.168.100.0 255.255.255.0
    default-router 192.168.100.1
    dns-server 8.8.8.8
    exit

Configure Access Point

  SSID--officewifi
  Security--WPA2-PSK
  Password--adnan1234

  
