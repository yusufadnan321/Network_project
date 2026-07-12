A small office network with one 2911 router, one 2960 switch, four pc


Ip Address table 
| Device | IP Address    | Subnet Mask   | Gateway      |
| ------ | ------------- | ------------- | ------------ |
| Router | 192.168.10.1  | 255.255.255.0 | —            |
| PC1    | 192.168.10.10 | 255.255.255.0 | 192.168.10.1 |
| PC2    | 192.168.10.11 | 255.255.255.0 | 192.168.10.1 |
| PC3    | 192.168.10.12 | 255.255.255.0 | 192.168.10.1 |
| PC4    | 192.168.10.13 | 255.255.255.0 | 192.168.10.1 |

cli command for router configuration

enable

configure terminal

hostname Office-Router

interface gigabitEthernet0/0

ip address 192.168.10.1 255.255.255.0

no shutdown

exit

end

