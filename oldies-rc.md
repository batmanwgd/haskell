## Non shallow brew: git -C '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask' fetch --unshallow
export BASH_SILENCE_DEPRECATION_WARNING=1

## Homebrew in Path
export PATH='/usr/local/sbin:$PATH'

## Homebrew Update/Reset
### alias brewrmv='brew remove --force $(brew list --formula) --ignore-dependencies'
### alias caskrmv='brew uninstall --cask --force $(brew list --cask)'
### alias brewcomprmv='/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall.sh)"'

## Fix Developer CLI
alias fixDev='sudo xcode-select -s /Applications/Xcode.app/Contents/Developer'

## Boot Stuff
alias boot='sudo nvram BootAudio=%01 && sudo nvram AutoBoot=%00'

## Default Shell Profile
### source ~/.bashrc

## GitShort
alias clone='git clone'
alias svn='colorsvn'

## Update Xcode Command Line Tools
alias update-x='softwareupdate --all --install --force'

## Fix Bad Xcode Command Line Tools Update
alias fix-cmd='sudo rm -rf /Library/Developer/CommandLineTools && sudo xcode-select --install'

## Disable Spotlight Indexing, to quit the mds service CPU hog
alias dmds='sudo mdutil -a -i off'

## Re-enable for whatever reason
alias rmds='sudo mdutil -a -i on'

# Save Directory
alias curDir="pwd | sed -e 's/ /\\ /'"
alias save='echo `curDir` > ~/.saved_dir'
alias saved='cd `cat ~/.saved_dir`'

## Edits to Profile
alias edit='sudo nano ~/.bashrc'
alias refresh='source ~/.bashrc'
alias review='cat ~/.bashrc'
alias backup='cat ~/.bashrc >> ~/.bashrc-bkup'

## Supress Apple's Warning About Bash
alias hushZSH='export BASH_SILENCE_DEPRECATION_WARNING=1'

## Modify the initial bash launch messge in the window
### remove the last login bits: touch .hushlogin into the main /Users/<username> directory
alias modOpen='sudo nano /etc/motd'

## Switch Bash to ZSH Back and Forth
alias bsh='chsh -s $(which bash)'
alias zsh='chsh -s $(which zsh)'
export PATH='/usr/local/opt/apr-util/bin:$PATH'

## ZSH to Bash Emulator -- Kinda Sucky
# emulate bash
# perform commands
# emulate -R zsh

## Reinstallation of X-Code CLI Tools
alias reX='sudo rm -rf $(xcode-select -print-path) && \
xcode-select --install'

## Reset the permissions for X-Code
alias accX='sudo xcodebuild -license accept'

## Power Administration Things
alias pingy='sudo hping3'
alias superman='sudo dsenableroot'
alias clarKent='sudo dsenableroot disable'
alias recovery='sudo nvram "recovery-boot-mode=unused" && sudo reboot'
alias pmsetVW='sudo pmset -g'
alias showBuild='sw_vers -productVersion'
alias sinceRst='uptime'
alias advSysRep='sudo sysdiagnose -f ~/Desktop/'
alias bawsCpy='echo "rsync rva /src/ /dest/"'
alias kernList='sudo kextstat -l'
alias viewMem='vm_stat -c 10 1'
alias search='mdfind -name "searchterm"'
# pmset -g batt | egrep '([0-9]+\%).*' -o --colour=auto | cut -f1 -d';' && \
# pmset -g batt | egrep '([0-9]+\%).*' -o --colour=auto | cut -f3 -d';' && \
alias welcomeScr='sudo defaults write /Library/Preferences/com.apple.loginwindow LoginwindowText "Isaiah 1:18"'
alias crashRep='defaults write com.apple.CrashReporter UseUNC 1'
alias mountSys='sudo mount -uw /'
alias showLib='chflags nohidden ~/Library/'
alias dnsFlush='sudo discoveryutil udnsflushcaches'
alias loginHost='sudo defaults write /Library/Preferences/com.apple.loginwindow AdminHostInfo HostName'

# Change login window screen message
# sudo defaults write /Library/Preferences/com.apple.loginwindow LoginwindowText

## Mini Resets
alias reFinder='sudo killall Finder'
alias undoCustom='defaults delete domain key'
alias reDock='sudo killall Dock'
alias reSysUI='sudo killall SystemUIServer'

## GitHub
alias up='git add -A && read && git commit -m '

## Finder, Files and Things
alias vwFiles='sudo fs_usage'
alias vmSnaps='tmutil localsnapshot'
alias vmSnapsDel='echo "tmutil deletelocalsnapshots com.apple.TimeMachine.2018-01-26-044042"'
alias vmSnapsVW='tmutil listlocalsnapshots /'
alias clrPrnt='cancel -a -'
alias compare='echo "diff -qr /path/to/folder1 /path/to/folder2"'
alias rmDS='defaults write com.apple.desktopservices DSDontWriteNetworkStores true'
alias mkDS='defaults write com.apple.desktopservices DSDontWriteNetworkStores false'
alias xpSave='defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true && \
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode2 -bool true'
alias showExt='defaults write NSGlobalDomain AppleShowAllExtensions -bool true'
alias proFinder='defaults write com.apple.finder QuitMenuItem -bool true && \
defaults write com.apple.finder DisableAllAnimations -bool true && \
defaults write com.apple.finder ShowPathbar -bool true && \
defaults write com.apple.finder ShowStatusBar -bool true && \
defaults write com.apple.finder FXDefaultSearchScope && \
defaults write com.apple.finder QLEnableTextSelection -bool true'
alias cleanDesk='defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true && \
defaults write com.apple.desktopservices DSDontWriteUSBStores -bool true && \
defaults write com.apple.finder CreateDesktop -bool false && killall Finder'

## Moving Around and Things
alias .='cd ../'
alias ..='cd ../../'
alias ...='cd ../../../'
alias ....='cd ../../../../'
alias ls='ls -lpa'

## SystemUI Things
alias ledFont='defaults write -g CGFontRenderingFontSmoothingDisabled -bool FALSE'
alias ledUndo='defaults write -g CGFontRenderingFontSmoothingDisabled -bool TRUE'
alias fontFactory='defaults -currentHost delete -globalDomain AppleFontSmoothing'
alias sprCol='defaults write com.apple.dock springboard-columns -int '
alias sprRow='defaults write com.apple.dock springboard-rows -int '
alias sprRef='defaults write com.apple.dock ResetLaunchPad -bool TRUE;killall Dock'
alias stopRevamp='defaults write com.apple.loginwindow TALLogoutSavesState -bool false && \
defaults write com.apple.loginwindow LoginwindowLaunchesRelaunchApps -bool false'
alias dkSpacer='defaults write com.apple.dock persistent-apps -array-add "{tile-data={}; tile-type="spacer-tile";}"'
#alias dkSpacer2='defaults write com.apple.dock persistent-others -array-add '{ "tile-data" \= \{\}\; "tile-type"\="small-spacer-tile"\; }'
alias proUI='defaults write -g NSAutomaticSpellingCorrectionEnabled -bool false && \
defaults write -g ApplePressAndHoldEnabled -bool true && \
defaults write NSGlobalDomain NSWindowResizeTime .001 && \
defaults write com.apple.Dock autohide-delay -float 0 && killall Dock && \
defaults write com.apple.Dock showhidden -bool YES && killall Dock && \
defaults write com.apple.dock expose-animation-duration -float 0.12 && killall Dock && \
defaults write com.apple.dock launchanim -bool false'

## Safari and Things
alias proSafari='defaults write com.apple.Safari WebKitInitialTimedLayoutDelay 0.25 && \
defaults write com.apple.Safari IncludeInternalDebugMenu -bool true && \
defaults write com.apple.Safari IncludeDevelopMenu -bool true && \
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true && \
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true'

## Copying Sites
alias copySite='wget -e robots=off -r -np -m -k -Ep'
alias copySiteRV='echo wget -e robots=off -r -np -m -k -Ep'
alias mirror='cd ~/Development/wgetCollections && \
wget -r -m -k -np -nc -c -Ep -P -e robots=off '

## Snapshots and Things
alias snaps='defaults -currentHost write com.apple.ImageCapture disableHotPlug -bool true && \
defaults write com.apple.screencapture name "Snaps"'

## Mail App and Things
alias proMail='defaults write com.apple.mail AddressesIncludeNameOnPasteboard -bool false && \
defaults write com.apple.mail DisableReplyAnimations -bool true && \
defaults write com.apple.mail DisableSendAnimations -bool true'

## NVM
export NVM_DIR='$HOME/.nvm'
  [ -s '/usr/local/opt/nvm/nvm.sh' ] && . '/usr/local/opt/nvm/nvm.sh'  # This loads nvm
  [ -s '/usr/local/opt/nvm/etc/bash_completion.d/nvm' ] && . '/usr/local/opt/nvm/etc/bash_completion.d/nvm'  # This loads nvm bash_completion

## Random Dev Bits
alias randomDev='defaults write -g WebKitDeveloperExtras -bool true && \
defaults write com.microsoft.VSCode ApplePressAndHoldEnabled -bool false'

## Add .NET Core SDK tools
export PATH='$PATH:/Users/kaska/.dotnet/tools'

## Nuget Setup
export MONO_GAC_PREFIX='/usr/local'

## Homebrew Setups and Simlinks
export RUBY_CONFIGURE_OPTS='--with-openssl-dir=$(brew --prefix openssl@1.1)'

## Brew tags
alias tag='tag --add '

## express
export PATH='/usr/local/Cellar/node/12.4.1/bin:$PATH'

## slack cli
PATH='/usr/local/opt/coreutils/libexec/gnubin:$PATH'

## OpenJDK
export PATH='/usr/local/opt/openjdk/bin:$PATH'
export CPPFLAGS='-I/usr/local/opt/openjdk/include'

## OpenSSL
export PATH='/usr/local/opt/openssl@1.1/bin:$PATH'
export LDFLAGS='-L/usr/local/opt/openssl@1.1/lib'
export CPPFLAGS='-I/usr/local/opt/openssl@1.1/include'

## pkg-config
export PKG_CONFIG_PATH='/usr/local/opt/readline/lib/pkgconfig'

## readline
export LDFLAGS='-L/usr/local/opt/readline/lib'
export CPPFLAGS='-I/usr/local/opt/readline/include'

## postgresql
export PKG_CONFIG_PATH='/usr/local/opt/postgresql@11/lib/pkgconfig'
export LDFLAGS='-L/usr/local/opt/postgresql@11/lib'
export CPPFLAGS='-I/usr/local/opt/postgresql@11/include'
export PATH='/usr/local/opt/postgresql@11/bin:$PATH'
# default cluster initdb --locale=C -E UTF-8 /usr/local/var/postgresql@11
# more info https://www.postgresql.org/docs/11/app-initdb.html

## libarchive
export PKG_CONFIG_PATH='/usr/local/opt/libarchive/lib/pkgconfig'
export LDFLAGS='-L/usr/local/opt/libarchive/lib'
export CPPFLAGS='-I/usr/local/opt/libarchive/include'
export PATH='/usr/local/opt/libarchive/bin:$PATH'

## mysql
export PKG_CONFIG_PATH='/usr/local/opt/mysql@5.7/lib/pkgconfig'
export LDFLAGS='-L/usr/local/opt/mysql@5.7/lib'
export CPPFLAGS='-I/usr/local/opt/mysql@5.7/include'
export PATH='/usr/local/opt/mysql@5.7/bin:$PATH'
# run connection mysql -uroot
# no root password setup, to secure run: mysql_secure_installation

## Ruby Installs, Builds and Environments
eval '$(rbenv init -)'
alias rbenvInitVW='rbenv init -' ## to view what happens under the hood of the above
export GEM_HOME='$HOME/gems'
export PATH='$HOME/gems/bin:$PATH'
# gem locale by default /usr/local/lib/ruby/gems/3.0.0/bin

## Ruby itself
export PATH='/usr/local/opt/ruby/bin:$PATH'
export PKG_CONFIG_PATH='/usr/local/opt/ruby/lib/pkgconfig'
export LDFLAGS='-L/usr/local/opt/ruby/lib'
export CPPFLAGS='-I/usr/local/opt/ruby/include'

## ssh copyid
export PATH='/usr/local/opt/ssh-copy-id/bin:$PATH'

## Git Shortcuts
### commit with date
alias tagIT='echo "git tag -a v.01272020 -m January 27, 2020 - Monday"'
alias tagDel='echo "git tag -d v.01272020"'
alias tagPsh='echo "git push origin v.01272020"'
alias tagUpt='echo "git tag -f -a v.01292020 && git push -f --tags"'
alias tagFgt='echo "please visit: https://git-scm.com/book/en/v2/Git-Basics-Tagging"'
alias up='git add -A && read msg && git commit -m $msg && git push origin HEAD:master'
alias up-light='git add -A && git commit -m "quick updates via term config" && git push origin HEAD:master'
alias pull='git fetch && git pull'

## Random Project Aliases and Simlinks
alias tanakh='cd /Users/kaska/Development/GitHub/Tanakh'
alias kaska='cd /Users/kaska/Development/kaska'
alias workrails='cd /Users/kaska/Development/workrails'
alias github='cd /Users/kaska/Development/GitHub'
alias covid='cd /Users/kaska/Batman\ Dropbox/C19_Smorgasbord/C19/'

## KRB5
export PATH='/usr/local/opt/krb5/bin:$PATH'
export PATH='/usr/local/opt/krb5/sbin:$PATH'
export LDFLAGS='-L/usr/local/opt/krb5/lib'
export CPPFLAGS='-I/usr/local/opt/krb5/include'
export PKG_CONFIG_PATH='/usr/local/opt/krb5/lib/pkgconfig'

export PATH='/usr/local/opt/apr/bin:$PATH'
export PATH='/usr/local/opt/apr-util/bin:$PATH'


## tesseract
export PATH='/usr/local/opt/gnu-getopt/bin:$PATH'

## Python Environment Managers
##'if command -v pyenv 1>/dev/null 2>&1; then\n  eval '$(pyenv init -)'\nfi'
if command -v pyenv 1>/dev/null 2>&1; then
  eval '$(pyenv init -)'
fi

alias pip='/usr/local/bin/pip3'


# getcwd error - system ruby gems update required
alias fixgetcwd='sudo gem update --system'

# Stack Haskell Path
# export PATH='/Users/kaska/.local/bin'

## openblas
export LDFLAGS='-L/usr/local/opt/openblas/lib'
export CPPFLAGS='-I/usr/local/opt/openblas/include'
export PKG_CONFIG_PATH='/usr/local/opt/openblas/lib/pkgconfig'

## gnubin
PATH='/usr/local/opt/coreutils/libexec/gnubin:$PATH'