# oh my zsh plugin for ansible

## install git, zsh, vim

yum install git zsh vim

## download oh-my-zsh

git clone https://github.com/robbyrussell/oh-my-zsh

## download ansible plugin

git clone https://github.com/sparsick/ansible-zsh oh-my-zsh/custom/plugins/ansible

## download zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-syntax-highlighting oh-my-zsh/custom/plugins/zsh-syntax-highlighting

## copy zshrc into home directory

cp sinog_ansible/zsh_ansible/zshrc .zshrc

## set user shell

chsh -s /bin/zsh

## change user shell

su - $USER

## test ansible plugin in zsh

ap --version

ansible-playbook 2.3.1.0
  config file = /etc/ansible/ansible.cfg
  configured module search path = Default w/o overrides
  python version = 2.7.5 (default, Nov  6 2016, 00:28:07) [GCC 4.8.5 20150623 (Red Hat 4.8.5-11)]

# Links

https://github.com/robbyrussell/oh-my-zsh

https://github.com/sparsick/ansible-zsh

https://github.com/zsh-users/zsh-syntax-highlighting
