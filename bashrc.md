#!/bin/bash

## Bash Silence Warning
export BASH_SILENCE_DEPRECATION_WARNING=1

## Fix Developer CLI
alias fixdv='sudo xcode-select -s /Applications/Xcode.app/Contents/Developer'

## Reinstallation of X-Code CLI Tools
alias rex='sudo rm -rf $(xcode-select -print-path) && \
xcode-select --install'

## Boot Stuff
alias boot='sudo nvram BootAudio=%01 && sudo nvram AutoBoot=%00'

## ghcup
### export PATH='/Users/kaska/.ghcup/env'
### alias ghcup='. $HOME/.ghcup/env'
export PATH="$HOME/.cabal/bin:$HOME/.ghcup/bin:$PATH"
### PATH="$HOME/.cabal/bin:$PATH"

## macports
### export PATH="/opt/local/bin:/opt/local/sbin:$PATH"

## Copying Sites
#alias copyste='wget -e robots=off -r -np -m -k -Ep'
#alias copysterv='echo wget -e robots=off -r -np -m -k -Ep'
#alias mirror='cd ~/Development/wgetCollections && \
#wget -r -m -k -np -nc -c -Ep -P -e robots=off '

## Moving Around and Things
alias .='cd ../'
alias ..='cd ../../'
alias ...='cd ../../../'
alias ....='cd ../../../../'
alias ls='ls -lpa'

## GitHub
alias gup='git add -A && read && git commit -m '
alias gcln='git clone'

## Switch Bash to ZSH Back and Forth
alias bsh='chsh -s $(which bash)'
alias zsh='chsh -s $(which zsh)'

## Edits to Profile
alias edit='sudo nano ~/.bashrc'
alias refresh='source ~/.bashrc'
alias review='cat ~/.bashrc'
alias backup='cat ~/.bashrc >> ~/.bashrc-bkup'

## Supress Apple's Warning About Bash
#alias hushZSH='export BASH_SILENCE_DEPRECATION_WARNING=1'

## MacPorts
export PATH=/opt/local/bin:/opt/local/sbin:$PATH
export MANPATH=/opt/local/share/man:$MANPATH
export EDITOR=/usr/bin/nano
alias ports='sudo port'

## POSIX
alias clr='clear'

# Finished adapting your PATH environment variable for use with MacPorts.

#### [[ -f ~/.bashrc ]] && source ~/.bashrc # ghcup-env
