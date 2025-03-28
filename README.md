# cisco_hazi

```bash

en
conf t
hostname R9

ip domain-name wmtech.hu
crypto key generate rsa 
1024

ip ssh version 2

username admin privilege 15 secret 1234

enable secret 1234
no ip domain-lookup 

line console 0
password 1234
exit

service password-encryption 

banner motd #Unauthorised access is prohibited!#

line vty 0 15
password 1234
transport input ssh 
login local 
exit

banner login #dobozolni a legjobb a vilagon ornagy#



int gig0/0
no sh
ip add 84.53.99.254 255.255.255.0
ex


int gig0/1
no sh
ip add 192.168.100.58 255.255.255.252
ex

int se0/0/0
no sh
ip add 192.168.100.46 255.255.255.252
ex

int se0/0/1
no sh
ip add 192.168.100.42 255.255.255.252
ex

router ospf 10
router-id 8.8.8.8
passive-interface g0/0
network 84.53.99.0 0.0.0.255 area 0
network 192.168.100.56 0.0.0.3 area 0
network 192.168.100.44 0.0.0.3 area 0
network 192.168.100.40 0.0.0.3 area 0

ex

end 

copy running-config startup-config 








```
