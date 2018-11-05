# osx

This is the installation guide how to install OSX according to my regular setup conventions.

## update

sudo softwareupdate -ia --verbose

## manual 
```
xcode
docker
```

## install brew and some packages

```
xcode-select --install
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install node
brew install watchman
brew install flow
brew install ruby
brew install autojump
brew install htop
brew install postman
brew install node
brew install wget
brew install yarn
brew install python
brew install nmap
brew install go
brew install tig
brew install hg bzr
brew install git
brew install vscode
brew install mysqlworkbench
brew install imageoptim
brew tap crisidev/homebrew-chunkwm
brew install --HEAD --with-tmp-logging chunkwm
brew install --HEAD --with-logging koekeishiya/formulae/skhd
brew services start chunkwm
brew services start koekeishiya/formulae/skhd
brew tap caskroom/cask
brew cask install java
brew install android-sdk android-ndk
brew install zsh zsh-completions
chsh -s /bin/zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
echo "export ANDROID_HOME=/usr/local/opt/android-sdk" >> ~/.zshrc
echo "export ANDROID_NDK=/usr/local/opt/android-ndk" >> ~/.zshrc
echo "alias xcode="open -a Xcode" >> ~/.zshrc
```

## git config
```
git config --global push.default simple
git config --global pull.rebase true
git config --global user.email "ptomasroos@gmail.com"
git config --global user.name "Tomas Roos"
```

## config osx
```
defaults write com.developer.application NSQuitAlwaysKeepsWindows -bool false
defaults write com.apple.screencapture location ~/Screenshots/
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
	'{"enabled" = 1;"name" = "MENU_EXPRESSION";}' \
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

#use another screen shot location to now pollute desktop
defaults write com.apple.screencapture location /Users/tomas/Documents/Screenshots

killall SystemUIServer
killall Finder
sudo find / -name '*.DS_Store' -type f -delete
```

## npm's
```
npm install -g react-native-cli
npm install -g http-server
```

## install gui applications

```
brew cask install vmware-fusion skype spotify google-chrome vlc slack dropbox firefox telegram sketch focus atom dashlane goofy android-studio
# remember to config on setup with sdk path /usr/local/opt/android-sdk on android-studio
echo "alias studio="open -a /Applications/Android\ Studio.app" >> ~/.zshrc # open android studio projects with "studio /directory"
```

```
xcode-select --install
```

## apm's
```
apm install nuclide
```
