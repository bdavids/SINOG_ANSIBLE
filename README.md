# Avtomatizirana konfiguracija omreznih naprav

# OS :

CentOS Linux release 7.3.1611 (Core)

# ANSIBLE :

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
