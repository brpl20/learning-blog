---
title: Debian Init e Instalacao Debian pkg tarz
layout: post
tags: [linux, debian]
---
# Configurando o Linux Debian Puro
1. Configurar o teclado é mais difícil (usando o padrão internacional pra usar o ç e acentos normalmente), o que funcionou aqui foi Ingles (Eua, int. alt.);
2. Su e Sudo são coisas diferentes. Para habilitar o sudo para seu usuário é preciso adicioa-lo no sudo através do su (O Su é o super usuário) ```adduser username sudo```;
3. É rápido pra caramba, então o esforço adicional de configuração compensa a longo prazo;
4. Estou com problemas para instalar o Bluetooth e o Wifi, logo abaixo em tópicos específicos;

# Plugins e Aliases do Oh My Zsh
1. git
2. gitfast
3. last-working-dir
3. [common-aliases](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/common-aliases)
4. sublime (stt)
5. [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)
6. history-substring-search
7. pyenv

## Aliases
- alias zshconfig="nvim ~/.zshrc"
- alias ohmyzsh="nvim ~/.oh-my-zsh"
- alias wikit="cd ~/code/wikit" #Wikit Pessoal ou Qualquer Coisa
- alias ~="cd ~"
- alias .="cd .."
- alias ..="cd ../.."
- alias ...="cd ../../.."
- alias ....="cd ../../../.."
- alias cd..="cd .."
- alias gd="cd ~/gd" #Google Drive 1
- alias gdesc="cd ~/gdesc" #Google Drive 2
- alias lla="ll -all"
- alias desk ; vai para o desktop
- alias down ; vai para os downloads

# Wifi & Bluetooth

# Instalação de Pacotes e Tars

## Comandos Para Instalação
[Debian Package (.deb)](https://unix.stackexchange.com/questions/159094/how-to-install-a-deb-file-by-dpkg-i-or-by-apt)
```
sudo dpkg -i /path/to/deb/file
sudo apt-get install -f
```
[Tar](https://sempreupdate.com.br/como-instalar-pacotes-programas-tar-gz-bz2-xz-no-linux/)
- tar -jxvf file.tar.bz2
- tar -Jxxvf file.tar.xz
- tar -zxvf  file.tar.gz

## [Snapcraft](https://snapcraft.io/)
- Snap pode ajudar a instalar alguns aplicativos, mas é um pouco instável dependendo do aplicativo melhor ir na `store` do próprio debian ou instalar pelo .deb ou .tar.


# Linux (em geral) Favorite app List - Criar Shell para baixa-los
- Flameshot (Screenshot)
- Wps Writer (Office)
- F.Lux
- Workrave
- Spotify
- VLC Player
- Ferramentas Básicas: Curl
- Ohmyzsh
- Sublime Text
- Nvim
- Firefox
- Chromium
