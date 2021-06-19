This is setup project to install and setup an linux enviroment and tools for my research.

The first ste is to install a latest version of Ubuntu and followed by install many software and tools to set up my personal ubuntu.

### Install latest Ubuntu
0) Download latest Ubuntu
1) Check your PC boot mode, legency or UEFI. if it is UEFI, then using GPT to make Ubuntu USB disk.
2) Depress some space to install ubuntu beside of your window OS.
3)  Insert Ubuntu USB disk and restart PC, click F12, and choose to start PC from USB
4) Install Ubuntu, follwoing this link https://www.cnblogs.com/masbay/p/10745170.html



### Install tools

1) install basic tools
sudo apt install git vim zsh terminator

2) setup tools
2.1) setup vima and install vim plugin
git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim

curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
cp ./vimrc ~/.vimrc

3.1) setup zsh

git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc


**plugin**
git clone https://github.com/zsh-users/zsh-completions ~/.oh-my-zsh/custom/plugins/zsh-completions
plugins=(… zsh-completions)

**configuration file**
# cat ~/.zshrc| grep -v "#"| grep -v "^$"
export ZSH=$HOME/.oh-my-zsh
ZSH_THEME="ys"
plugins=(git   colored-man-pages  zsh_reload sudo zsh-completions autojump zsh-autosuggestions)
source $ZSH/oh-my-zsh.sh

#source ~/.oh-my-zsh/plugins/incr/incr*.zsh
source ~/.oh-my-zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
[[ -s ~/.autojump/etc/profile.d/autojump.sh ]] && . ~/.autojump/etc/profile.d/autojump.sh
autoload -U compinit && compinit -u


#### Install pyenv and pyenv-virtual 

1) Install 
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"'
echo 'eval "$(pyenv init --path)"'
echo 'eval "$(pyenv virtualenv-init -)"'

2) Setup

mkdir -p ~/workspace/PythonProject/; cd ~/workspace/PythonProject/
git clone https://gitlab.com/sunzhon/DataAnalysis.git

%pyenv environemt

mkdir -p ~/.pyenv/cache
v=3.9.2|wget http://mirrors.sohu.com/python/$v/Python-$v.tar.xz -P ~/.pyenv/cache/;pyenv install $v

pyenv virtualenv 3.9.2 DataVisulization
pyenv activate DataVisulization
sudo apt install python3-pip3

pip3 install numpy
pip3 install pandas
pip3 install matplotlib
pip3 install tensorflow
pip3 install 

#### Install latex and latexmk 



### Install 
