# osx

This is the installation guide how to install OSX according to my regular setup conventions.

## update

sudo softwareupdate -ia --verbose

## manual 
```
xcode
xcode-select --install
```

## install brew and some packages

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

```
brew install zsh zsh-completion
chsh -s /bin/zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## continue with more brew packages

```
brew install node watchman autojump htop wget nmap yarn tig hg bzr git
echo "export ANDROID_HOME=/usr/local/opt/android-sdk" >> ~/.zshrc
echo "export ANDROID_NDK=/usr/local/opt/android-ndk" >> ~/.zshrc
echo "alias xcode="open -a Xcode" >> ~/.zshrc
echo "alias studio="open -a /Applications/Android\ Studio.app" >> ~/.zshrc
```

## i3wm-look-alike on mac
```
brew tap crisidev/homebrew-chunkwm
brew install --HEAD --with-tmp-logging chunkwm
brew install --HEAD --with-logging koekeishiya/formulae/skhd
brew services start chunkwm
brew services start koekeishiya/formulae/skhd
```

```
brew tap wix/brew
brew install applesimutils
```

## brew casks
```
brew cask install atom java docker android-sdk homebrew/cask-versions/java8 android-ndk visual-studio-code skype spotify google-chrome vlc slack dropbox firefox telegram focus goofy signal android-studio spectrum discord
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
defaults write com.apple.mouse.tapBehavior -int 1
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES
defaults write com.apple.finder AppleShowAllFiles TRUE
defaults write com.apple.finder QuitMenuItem -bool true
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"
defaults write com.apple.Finder QuitMenuItem -bool YES
defaults write AppleShowAllExtensions -bool true
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool true
defaults write NSAutomaticSpellingCorrectionEnabled -bool false
defaults write com.apple.screensaver askForPassword -int 1
defaults write com.apple.screensaver askForPasswordDelay -int 0
defaults write com.apple.Safari HomePage -string "about:blank"
defaults write com.apple.Safari ShowSidebarInTopSites -bool false
defaults write com.apple.Safari ShowFavoritesBar -bool false
defaults write com.apple.Safari IncludeDevelopMenu -bool true
defaults write com.apple.Safari WebKitDeveloperExtrasEnabledPreferenceKey -bool true
defaults write com.apple.Safari com.apple.Safari.ContentPageGroupIdentifier.WebKit2DeveloperExtrasEnabled -bool true
defaults write com.apple.mail DisableReplyAnimations -bool true
defaults write com.apple.mail DisableSendAnimations -bool true
defaults write com.apple.mail AddressesIncludeNameOnPasteboard -bool false
```

## npm's
```
npm install -g react-native-cli
npm install -g detox-cli
```

## install gui applications

```
brew cask install vmware-fusion skype spotify google-chrome vlc slack dropbox firefox telegram sketch focus atom dashlane goofy android-studio spectrum signal discord
# remember to config on setup with sdk path /usr/local/opt/android-sdk on android-studio
```

## apm's
```
apm install nuclide
```
