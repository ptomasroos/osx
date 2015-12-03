# osx

This is the installation guide how to install OSX according to my regular setup conventions.

## update

sudo softwareupdate -iva

## manual 
```
xcode
```

## install brew and some packages

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install caskroom/cask/brew-cask
brew install node
brew install watchman
brew install flow
brew install android-sdk android-ndk
brew install zsh zsh-completions
chsh -s /bin/zsh
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
echo "export ANDROID_HOME=/usr/local/opt/android-sdk" >> ~/.zshrc
```

## config osx
```
defaults write com.developer.application NSQuitAlwaysKeepsWindows -bool false
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES
defaults write com.apple.finder AppleShowAllFiles TRUE
defaults write AppleShowAllExtensions -bool true
defaults write com.apple.Finder QuitMenuItem -bool YES
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool true
defaults write com.apple.mouse.tapBehavior -int 1
defaults write NSAutomaticSpellingCorrectionEnabled -bool false
defaults write com.apple.screensaver askForPassword -int 1
defaults write com.apple.screensaver askForPasswordDelay -int 0
defaults write com.apple.finder QuitMenuItem -bool true
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"
defaults write com.apple.Safari HomePage -string "about:blank"
defaults write com.apple.Safari ShowSidebarInTopSites -bool false
defaults write com.apple.Safari ShowFavoritesBar -bool false
defaults write com.apple.Safari IncludeDevelopMenu -bool true
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true
defaults write com.apple.mail DisableReplyAnimations -bool true
defaults write com.apple.mail DisableSendAnimations -bool true
defaults write com.apple.mail AddressesIncludeNameOnPasteboard -bool false

defaults write com.apple.spotlight orderedItems -array \
	'{"enabled" = 1;"name" = "APPLICATIONS";}' \
	'{"enabled" = 1;"name" = "SYSTEM_PREFS";}' \
	'{"enabled" = 1;"name" = "DIRECTORIES";}' \
	'{"enabled" = 0;"name" = "PDF";}' \
	'{"enabled" = 0;"name" = "FONTS";}' \
	'{"enabled" = 0;"name" = "DOCUMENTS";}' \
	'{"enabled" = 0;"name" = "MESSAGES";}' \
	'{"enabled" = 0;"name" = "CONTACT";}' \
	'{"enabled" = 0;"name" = "EVENT_TODO";}' \
	'{"enabled" = 0;"name" = "IMAGES";}' \
	'{"enabled" = 0;"name" = "BOOKMARKS";}' \
	'{"enabled" = 0;"name" = "MUSIC";}' \
	'{"enabled" = 0;"name" = "MOVIES";}' \
	'{"enabled" = 0;"name" = "PRESENTATIONS";}' \
	'{"enabled" = 0;"name" = "SPREADSHEETS";}' \
	'{"enabled" = 0;"name" = "SOURCE";}' \
	'{"enabled" = 0;"name" = "MENU_DEFINITION";}' \
	'{"enabled" = 0;"name" = "MENU_OTHER";}' \
	'{"enabled" = 0;"name" = "MENU_CONVERSION";}' \
	'{"enabled" = 0;"name" = "MENU_EXPRESSION";}' \
	'{"enabled" = 0;"name" = "MENU_WEBSEARCH";}' \
	'{"enabled" = 0;"name" = "MENU_SPOTLIGHT_SUGGESTIONS";}'

# Load new settings before rebuilding the index
killall mds > /dev/null 2>&1
# Make sure indexing is enabled for the main volume
sudo mdutil -i on / > /dev/null
# Rebuild the index from scratch
sudo mdutil -E / > /dev/null

#use UTF8 in terminal
defaults write com.apple.terminal StringEncodings -array 4


killall Finder
sudo find / -name '*.DS_Store' -type f -delete
```

## npm's
```
npm install -g react-native-cli
npm install -g http-server
```

#install gui applications

```
brew cask install vmware-fusion
brew cask install skype
brew cask install spotify
brew cask install google-chrome
brew cask install vlc
brew cask install evernote
brew cask install slack
brew cask install bitcoin-core
brew cask install dropbox
brew cask install screenhero
brew cask install firefox
brew cask install telegram
brew cask install sketch
brew cask install genymotion # remember to configure to use the SDK at /usr/local/opt/android-sdk
brew cask install java
brew cask install android-studio # remember to config on setup with sdk path /usr/local/opt/android-sdk
brew cask install microsoft-office365
brew cask install google-drive
brew cask install focus
brew cask install atom
brew cask install dashlane
brew cask install teamviewer
```

```
sudo gem install cocoapods
```

