# 配置linux - LhamoJam
<!-- TOC -->

- [配置linux - LhamoJam](#配置linux---lhamojam)
- [前置设置](#前置设置)
  - [遇到 NO_PUBKEY 9334A25F8507EFA5 的解法](#遇到-no_pubkey-9334a25f8507efa5-的解法)
- [安装基础组件](#安装基础组件)
- [终端优化](#终端优化)
  - [oh my zsh](#oh-my-zsh)
    - [安装oh-my-zsh](#安装oh-my-zsh)
    - [安装Nerd Fonts字体(1个G)](#安装nerd-fonts字体1个g)
    - [安装Powerlevel0k](#安装powerlevel0k)
    - [安装命令行工具](#安装命令行工具)
- [软件安装](#软件安装)
  - [Neovim](#neovim)
  - [Anaconda](#anaconda)
  - [code-server](#code-server)
  - [nodejs](#nodejs)

<!-- /TOC -->
# 前置设置

设置临时端口转发到VPN梯子软件Clash

- win:

    ```shell
    set https_proxy=https://192.168.31.20:7890
    set http_proxy=http://192.168.31.20:7890`
    ```

- linux:

    ```shell
    export https_proxy=https://192.168.43.19:7890
    export http_proxy=http://192.168.43.19:7890
    ```

## 遇到 NO_PUBKEY 9334A25F8507EFA5 的解法

- 解法:
  - `sudo apt-key adv --keyserver keys.gnupg.net --recv-keys <PUBKEY>`
  - `sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys <PUBKEY>`
  **註**：解法有很多種，在這邊只紀錄最簡單一行的版本
- 方法2 (两行版):

    ```shell
    gpg --keyserver keys.gnupg.net --recv-key 112695A0E562B32A
    gpg -a --export 112695A0E562B32A | sudo apt-key add -
    ```

# 安装基础组件

- `sudo apt-get update`
- `sudo apt-get install neovim openssh curl wget git gcc g++ make cmake python3-dev cython`

# 终端优化

## oh my zsh

```shell
sudo apt-get install zsh
chsh -s /bin/zsh
```

### 安装oh-my-zsh

- **curl** 安装: `sudo sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
- wget 安装: `sudo sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"`
- **<font style="color:red;">[ ! ]</font>** 安装失败，可以先用git下载:
  - `git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh`
  - 再替换zshrc: `cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc`

### [安装Nerd Fonts字体(1个G)](https://www.cnblogs.com/hongdada/p/14031915.html)

```shell
mkdir -p ~/.local/share/fonts cd ~/.local/share/fonts && curl -fLo "Droid Sans Mono for Powerline Nerd Font Complete.otf"

https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/DroidSansMono/complete/Droid%20Sans%20Mono%20Nerd%20Font%20Complete.otf
```

- 生成字体信息缓存 `fc-cache -vf ~/.local/share/fonts/`
- 查看是否安装成功 `fc-list | grep -i droid /home/kylin/.local/share/fonts/Droid Sans Mono for Powerline Nerd Font Complete.otf: DroidSansMonoForPowerline Nerd Font:style=Book`
- **<font style="color:red;">[ ! ]</font>** 小字体:`sudo apt-get install fonts-powerline`

### [安装Powerlevel0k](https://blog.csdn.net/kk3909/article/details/105120234/)

- `sudo git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k`
- 编辑`sudo vim ~/.zshrc`

   ```shell
   ZSH_THEME="powerlevel10k/powerlevel10k"
   POWERLEVEL9K_MODE="awesome-patched"
   ```

- 配置文件生效: `source ~/.zshrc`

### 安装命令行工具

- `sudo apt-get install fzf thefuck autojump`
- 语法高亮: `sudo apt-get install zsh-syntax-highlighting`
- 自动补全: `sudo git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`

# 软件安装

## Neovim

## Anaconda

## code-server

## nodejs