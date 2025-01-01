# osx

This is the installation guide how to install OSX according to my regular setup conventions.

## update

```
sudo softwareupdate -ia --verbose
```

## xcode tools
```
xcode-select --install
```

## install brew

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```
brew install zsh
chsh -s $(which zsh)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## continue with more brew packages

```
brew install pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init - zsh)"' >> ~/.zshrc

brew install nodenv
echo 'eval "$(nodenv init - zsh)"' >> ~/.zshrc

brew install goenv
echo 'eval "$(goenv init -)"' >> ~/.zshrc

brew install rbenv
echo 'eval "$(rbenv init -)"' >> ~/.zshrc

brew install watchman autojump htop wget nmap tig git tree xz uv ripgrep fzf

echo "export ANDROID_HOME=/Users/tomas/Library/Android/sdk" >> ~/.zshrc
echo "export ANDROID_NDK=/Users/tomas/Library/Android/sdk/ndk-bundle" >> ~/.zshrc
echo "alias xcode=\"open -a Xcode\"" >> ~/.zshrc
echo "alias studio=\"open -a /Applications/Android\ Studio.app\"" >> ~/.zshrc
echo "export LC_ALL=en_US.UTF-8" >> ~/.zshrc
echo "export LANG=en_US.UTF-8" >> ~/.zshrc
echo 'eval "$(uv generate-shell-completion zsh)"

_uv_run_mod() {
    if [[ "$words[2]" == "run" && "$words[CURRENT]" != -* ]]; then
        _arguments "\*:filename:_files"
    else
        _uv "$@"
    fi
}
compdef _uv_run_mod uv
' >> ~/.zshrc

echo "HISTFILE=~/.zsh_history" >> ~/.zshrc
echo "HISTSIZE=999999999" >> ~/.zshrc
echo "SAVEHIST=$HISTSIZE" >> ~/.zshrc

echo "source <(fzf --zsh)" >> ~/.zshrc
```

## brew casks
```
brew install --cask xbar chatgpt imageoptim nordvpn docker visual-studio-code spotify google-chrome vlc slack firefox telegram signal android-studio spectrum discord
```

## google-cloud-sdk
```
brew install --cask google-cloud-sdk
echo 'source "/usr/local/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/path.zsh.inc"' >> ~/.zshrc
echo 'source "/usr/local/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/completion.zsh.inc"' >> ~/.zshrc

```

## git config
```
mkdir -p ~/.ssh
git config --global push.default simple
git config --global pull.rebase true
git config --global user.email "ptomasroos@gmail.com"
git config --global user.name "Tomas Roos"
```

## config osx
```

# trackpad: enable tap to click
defaults write NSGlobalDomain com.apple.mouse.tapBehavior -int 1

# set bluetooth trackpad to tap
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool YES

# show hidden files
defaults write com.apple.finder AppleShowAllFiles -bool YES

# display full POSIX path as Finder window title
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES

# allow finder to quit
defaults write com.apple.finder QuitMenuItem -bool YES
  
# show all file extensions
defaults write NSGlobalDomain AppleShowAllExtensions -bool YES

# show status bar
defaults write com.apple.finder ShowStatusBar -bool YES

# show path bar
defaults write com.apple.finder ShowPathbar -bool true

# enable text selection in QuickLook
defaults write com.apple.finder QLEnableTextSelection -bool true

# when searching, search the current folder by default
defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"

# disable file extension warning
defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false

# wipe all (default) app icons from the 
defaults write com.apple.dock persistent-apps -array
killall Dock

# set Dock to auto-hide and remove the auto-hiding delay
defaults write com.apple.dock autohide -bool true
defaults write com.apple.dock autohide-delay -float 0
defaults write com.apple.dock autohide-time-modifier -float 0

# don't create .DS_Store files on network volumes
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

# arrange by kind
defaults write com.apple.finder FXArrangeGroupBy -string "kind"

# use list view by default
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"

# using the system-native print preview dialog in Chrome
defaults write com.google.Chrome DisablePrintPreview -bool true

# disable the all too sensitive backswipe on trackpads
defaults write com.google.Chrome AppleEnableSwipeNavigateWithScrolls -bool false

# expand the print dialog by default
defaults write com.google.Chrome PMPrintingExpandedStateForPrint2 -bool true

# enable the automatic update check
defaults write com.apple.SoftwareUpdate AutomaticCheckEnabled -bool true

# check for software updates daily, not just once per week
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

# download newly available updates in background
defaults write com.apple.SoftwareUpdate AutomaticDownload -int 1

# install System data files & security updates
defaults write com.apple.SoftwareUpdate CriticalUpdateInstall -int 1

# turn on app auto-update
defaults write com.apple.commerce AutoUpdate -bool true

# allow the App Store to reboot machine on macOS updates
defaults write com.apple.commerce AutoUpdateRestartRequired -bool true

# set screenshots dir to avoid polluting the desktop
mkdir -p "${HOME}/Screenshots"
defaults write com.apple.screencapture location -string "${HOME}/Screenshots"

# set default format for screenshots
defaults write com.apple.screencapture type -string "png"

# copy emails as 'foo@example.com', not 'Foo Bar <foo@example.com'
defaults write com.apple.mail AddressesIncludeNameOnPasteboard -bool false

# disable send and reply animations in Mail.app
defaults write com.apple.mail DisableReplyAnimations -bool true
defaults write com.apple.mail DisableSendAnimations -bool true

# disable inline attachments (just show the icons)
defaults write com.apple.mail DisableInlineAttachmentViewing -bool true

# only use uft-8 in Terminal.app
defaults write com.apple.terminal StringEncodings -array 4

# expanding the save panel by default
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true
defaults write NSGlobalDomain PMPrintingExpandedStateForPrint -bool true
defaults write NSGlobalDomain PMPrintingExpandedStateForPrint2 -bool true

# automatically quit printer app once the print jobs complete
defaults write com.apple.print.PrintingPrefs "Quit When Finished" -bool true

# save to disk, rather than iCloud, by default
defaults write NSGlobalDomain NSDocumentSaveNewDocumentsToCloud -bool false

# disable Photos.app from starting everytime a device is plugged in
defaults write com.apple.ImageCapture disableHotPlug -bool true

# disable system-wide resume
defaults write com.apple.systempreferences NSQuitAlwaysKeepsWindows -bool false

# requiring password immediately after sleep or screen saver begins
defaults write com.apple.screensaver askForPassword -int 1
defaults write com.apple.screensaver askForPasswordDelay -int 0

# don’t show recent applications in Dock
defaults write com.apple.dock show-recents -bool false

```
