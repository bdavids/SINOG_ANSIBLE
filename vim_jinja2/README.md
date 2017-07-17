# add jinja2 syntax support to vim

yum install vim

mv /usr/bin/vi /usr/bin/vi-old

ln -s /usr/bin/vim /usr/bin/vi

mkdir -p ~/.vim/bundle/

git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim

## edit vimrc

set nocompatible

syntax on

filetype on

set rtp+=~/.vim/bundle/Vundle.vim/

call vundle#begin()

call vundle#end()

Bundle "lepture/vim-jinja"

au BufNewFile,BufRead *.j2 set ft=jinja

## run vim

vim

:BundleInstall

# Links

https://github.com/lepture/vim-jinja
