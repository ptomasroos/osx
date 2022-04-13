# osx

This is the installation guide how to install OSX according to my regular setup conventions.

## update

```
sudo softwareupdate -ia --verbose
```

## manual from appstore
```
1password
xcode
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
brew install zsh zsh-completion
chsh -s /bin/zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## continue with more brew packages

```
brew install nvm watchman autojump htop wget nmap yarn tig hg bzr git goenv tree
echo "eval \"$(goenv init -)\"" >> ~/.zshrc
source ~/.zshrc
mkdir ~/.nvm
echo "export NVM_DIR=\"$HOME/.nvm\"" >> ~/.zshrc
echo ". \"$(brew --prefix nvm)/nvm.sh\"" >> ~/.zshrc
source ~/.zshrc
nvm install node
nvm use node
echo "export ANDROID_HOME=/Users/tomas/Library/Android/sdk" >> ~/.zshrc
echo "export ANDROID_NDK=/Users/tomas/Library/Android/sdk/ndk-bundle" >> ~/.zshrc
echo "alias xcode=\"open -a Xcode\"" >> ~/.zshrc
echo "alias studio=\"open -a /Applications/Android\ Studio.app\"" >> ~/.zshrc
echo "export GOPATH=$HOME/go" >> ~/.zshrc
echo "export GEM_HOME=/Users/tomas/.gem" >> ~/.zshrc
echo "export PATH=\"$GEM_HOME/bin:$PATH\"" >> ~/.zshrc
echo "export LC_ALL=en_US.UTF-8" >> ~/.zshrc
echo "export LANG=en_US.UTF-8" >> ~/.zshrc
source ~/.zshrc
mkdir -p $GOPATH
```

## i3wm-look-alike on mac
```
brew install --HEAD --with-tmp-logging koekeishiya/formulae/chunkwm
brew install --HEAD --with-logging koekeishiya/formulae/skhd
brew services start koekeishiya/formulae/chunkwm
brew services start koekeishiya/formulae/skhd
wget https://raw.githubusercontent.com/ptomasroos/osx/master/.skhdrc ~/.skhdrc
wget https://raw.githubusercontent.com/ptomasroos/osx/master/.chunkwmrc ~/.chunkwmrc
chmod +x ~/.chunkwmrc
brew services restart koekeishiya/formulae/chunkwm
brew services restart koekeishiya/formulae/skhd
```

```
gem install bundler
brew tap wix/brew
brew install applesimutils
```

## brew casks
```
brew cask install homebrew/cask-versions/java8
brew cask install microsoft-office
brew cask install imageoptim bitbar shimo nordvpn ngrok vmware-fusion atom docker visual-studio-code skype spotify google-chrome vlc slack dropbox firefox telegram focus goofy signal android-studio spectrum discord google-cloud-sdk
echo "source '/usr/local/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/path.zsh.inc'" >> ~/.zshrc
echo "source '/usr/local/Caskroom/google-cloud-sdk/latest/google-cloud-sdk/completion.zsh.inc'" >> ~/.zshrc
source ~/.zshrc
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
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool YES
defaults -currentHost write NSGlobalDomain com.apple.mouse.tapBehavior -int 1
defaults write NSGlobalDomain com.apple.mouse.tapBehavior -int 1

# automatically illuminate built-in keyboard in low light
defaults write com.apple.BezelServices kDim -bool YES
# but go dark after 5mins of inactivity
defaults write com.apple.BezelServices kDimTime -int 300

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

# wipe all (default) app icons from the Dock
defaults write com.apple.dock persistent-apps -array

# set Dock to auto-hide and remove the auto-hiding delay
defaults write com.apple.dock autohide -bool true
defaults write com.apple.dock autohide-delay -float 0
defaults write com.apple.dock autohide-time-modifier -float 0

# enable spring loading for directories, remove the delay
defaults write NSGlobalDomain com.apple.springing.enabled -bool true
defaults write NSGlobalDomain com.apple.springing.delay -float 0

# don't create .DS_Store files on network volumes
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true

# arrange by kind
/usr/libexec/PlistBuddy -c "Set :DesktopViewSettings:IconViewSettings:arrangeBy kind" ~/Library/Preferences/com.apple.finder.plist
/usr/libexec/PlistBuddy -c "Set :FK_StandardViewSettings:IconViewSettings:arrangeBy kind" ~/Library/Preferences/com.apple.finder.plist
/usr/libexec/PlistBuddy -c "Set :StandardViewSettings:IconViewSettings:arrangeBy kind" ~/Library/Preferences/com.apple.finder.plist

# set grid spacing
/usr/libexec/PlistBuddy -c "Set :DesktopViewSettings:IconViewSettings:gridSpacing 54" ~/Library/Preferences/com.apple.finder.plist
/usr/libexec/PlistBuddy -c "Set :FK_StandardViewSettings:IconViewSettings:gridSpacing 54" ~/Library/Preferences/com.apple.finder.plist
/usr/libexec/PlistBuddy -c "Set :StandardViewSettings:IconViewSettings:gridSpacing 30" ~/Library/Preferences/com.apple.finder.plist

# use icon view by default
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"

# don't open 'safe' files by default
defaults write com.apple.Safari AutoOpenSafeDownloads -bool false

# set Safari's page search to 'contains' not 'starts with'
defaults write com.apple.Safari FindOnPageMatchesWordStartsOnly -bool false

# safari's homepage to bogus
defaults write com.apple.Safari HomePage -string "about:blank"

# disabling Safari's thumbnail cache for History and Top Sites"
defaults write com.apple.Safari DebugSnapshotsUpdatePolicy -int 2

# disable the default top sites in new tabs
defaults write com.apple.Safari ShowSidebarInTopSites -bool false

# remove the top sticky favorites bar
defaults write com.apple.Safari ShowFavoritesBar -bool false

# enable Develop menu and Web Inspector
defaults write com.apple.Safari IncludeDevelopMenu -bool true
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true

# disable AutoFill in safari
defaults write com.apple.Safari AutoFillFromAddressBook -bool false
defaults write com.apple.Safari AutoFillPasswords -bool false
defaults write com.apple.Safari AutoFillCreditCardData -bool false
defaults write com.apple.Safari AutoFillMiscellaneousForms -bool false

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

# automatically download apps purchased on other Macs
defaults write com.apple.SoftwareUpdate ConfigDataInstall -int 1

# turn on app auto-update
defaults write com.apple.commerce AutoUpdate -bool true

# allow the App Store to reboot machine on macOS updates
defaults write com.apple.commerce AutoUpdateRestartRequired -bool true

# adding a context menu item for showing the Web Inspector in web views"
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# show web inspector in all other web views
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# set screenshots dir to avoid polluting the desktop
mkdir -p "${HOME}/Screenshots"
defaults write com.apple.screencapture location -string "${HOME}/Screenshots"

# set default format for screenshots
defaults write com.apple.screencapture type -string "png"

# enabling subpixel font rendering on non-Apple LCDs
defaults write NSGlobalDomain AppleFontSmoothing -int 2

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

# check for software updates daily, not just once per week
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

# check for software updates daily, not just once per week
defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1

# disable Photos.app from starting everytime a device is plugged in
defaults -currentHost write com.apple.ImageCapture disableHotPlug -bool true

# disable system-wide resume
defaults write com.apple.systempreferences NSQuitAlwaysKeepsWindows -bool false

# set bluetooth trackpad to tap
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool true

# requiring password immediately after sleep or screen saver begins
defaults write com.apple.screensaver askForPassword -int 1
defaults write com.apple.screensaver askForPasswordDelay -int 0

# disable local Time Machine backups
sudo tmutil disable

# don’t show recent applications in Dock
defaults write com.apple.dock show-recents -bool false

```

## npm's
```
npm install -g react-native-cli
npm install -g detox-cli
```

## pip's
```
pip install virtualenv
```
