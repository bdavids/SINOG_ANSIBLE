# add jinja2 syntax support to vim

yum install vim

mv /usr/bin/vi /usr/bin/vi-old

ln -s /usr/bin/vim /usr/bin/vi

mkdir -p ~/.vim/bundle/

git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim

## copy vimrc into home direcotry

cp sinog_ansible/vim_jinja2/vimrc .vimrc

## change shell

su - $USER

## run vim

vim

:BundleInstall

# Links

https://github.com/lepture/vim-jinja
