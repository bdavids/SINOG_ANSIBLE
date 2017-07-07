# Automated configuration of network devices

## OS :

CentOS Linux release 7.3.1611 (Core)

## ANSIBLE :

yum -y install epel-release

yum -y install gcc libffi-devel python-devel openssl-devel

yum -y install python-pip

pip install --upgrade pip

pip install -U setuptools

yum -y install ansible

ansible --version

ansible 2.3.1.0
  config file = /etc/ansible/ansible.cfg
  configured module search path = Default w/o overrides
  python version = 2.7.5 (default, Nov  6 2016, 00:28:07) [GCC 4.8.5 20150623 (Red Hat 4.8.5-11)]

## run ansible scripts

### open file with password (sinog)

ansible-vault encrypt secure/ssh_user


### generate config files

ansible-playbook config_cisco_l3.yml --ask-vault --tags "config"

ansible-playbook config_cisco_l2.yml --ask-vault --tags "config"

ansible-playbook config_smb_l2.yml --ask-vault --tags "config"

### partial switch config

ls configs/sw_cisco_l3/cisco-l3/

ls configs/sw_cisco_l2/cisco-l2/

ls configs/sw_smb_l2/smb-l2/

### complete switch config

cat configs/sw_cisco_l3/cisco-l3.cfg

cat configs/sw_cisco_l2/cisco-l2.cfg

cat configs/sw_smb_l2/smb-l2.cfg

### deploy configs files to switch

ansible-playbook config_cisco_l3.yml --ask-vault --tags "deploy"

ansible-playbook config_cisco_l2.yml --ask-vault --tags "deploy"

ansible-playbook config_smb_l2.yml --ask-vault --tags "deploy"

# Links

 https://github.com/ubajze/ansible_workshop

 https://github.com/ipspace/NetOpsWorkshop

 https://pynet.twb-tech.com/

 https://github.com/napalm-automation/napalm

 https://github.com/dravetech/napalm-ansible-tutorial
