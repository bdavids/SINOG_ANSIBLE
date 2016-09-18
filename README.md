Avtomatizirana konfiguracija omreznih naprav

OS :

Debian GNU/Linux 8 \n \l

Instalacija Ansible :

https://gist.github.com/trinitronx/bdfd3cbb338767e58299

chmod u+x ansible_install.sh
./ansible_install.sh

ansible --version
ansible 2.1.1.0
  config file = 
  configured module search path = Default w/o overrides
  
Konfiguracija CISCO stikala (zacetna) :

  vtp mode off

  vlan 50
  
  interface vlan 50
    ip address 192.168.50.10 255.255.255.0
    no shutdown
    
  ip default-gateway 192.168.50.1

  interface GigabitEthernet1/1/1
   switchport trunk encapsulation dot1q
   switchport trunk allowed vlan 50
   switchport mode trunk
   no shutdown

  ip domain-name sinog.si
  hostname SINOG-CISCO
  
  ip ssh version 2

  crypto key generate rsa general-keys modulus 2048

  aaa new-model
  aaa authentication login default local
  aaa authorization console
  aaa authorization exec default local

  username sinog privilege 15 secret sinog
  
Konfiguracija SMB stikala (zacetna) :

 vlan 50

 interface vlan 50
  name MGMT
  ip address 192.168.50.100 255.255.255.0
  no shutdown
    
 ip default-gateway 192.168.50.1
 
 interface Gigabitethernet49
   switchport trunk allowed vlan add 50
   switchport mode trunk
   
 ip ssh password-auth
 ip ssh server 
 
 username sinog privilege 15 password sinog

Links :
 
 https://github.com/ubajze/ansible_workshop
 
 https://github.com/ipspace/NetOpsWorkshop
