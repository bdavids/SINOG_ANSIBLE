# Avtomatizirana konfiguracija omreznih naprav

# OS :

CentOS Linux release 7.3.1611 (Core)

# ANSIBLE :

yum install epel-release

yum -y install gcc libffi-devel python-devel openssl-devel

yum -y install python-pip

pip install --upgrade pip

pip install -U setuptools

yum install ansible

ansible --version

ansible 2.3.1.0
  config file = /etc/ansible/ansible.cfg
  configured module search path = Default w/o overrides
  python version = 2.7.5 (default, Nov  6 2016, 00:28:07) [GCC 4.8.5 20150623 (Red Hat 4.8.5-11)]

  
# Konfiguracija CISCO stikala (zacetna) :

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
  
   switchport nonegotiate
   
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
  
# Konfiguracija SMB stikala (zacetna) :

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
 
 snmp-server engineid local default
 
 username sinog privilege 15 password sinog

# Links :
 
 https://github.com/ubajze/ansible_workshop
 
 https://github.com/ipspace/NetOpsWorkshop
