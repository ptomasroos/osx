# osx

This is the installation guide how to install OSX according to my regular setup conventions.

## update

sudo softwareupdate -ia --verbose

## manual from appstore
```
dashlane
xcode
xcode-select --install
```

## install brew

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
brew install nvm watchman autojump htop wget nmap yarn tig hg bzr git goenv tree
echo "eval \"$(goenv init -)\"" >> ~/.zshrc
source ~/.zshrc
mkdir ~/.nvm
echo "export NVM_DIR=\"$HOME/.nvm\"" >> ~/.zshrc
echo ". \"$(brew --prefix nvm)/nvm.sh\"" >> ~/.zshrc
source ~/.zshrc
nvm install node
nvm use node
echo "export ANDROID_HOME=/usr/local/opt/android-sdk" >> ~/.zshrc
echo "export ANDROID_NDK=/usr/local/opt/android-ndk" >> ~/.zshrc
echo "alias xcode=\"open -a Xcode\"" >> ~/.zshrc
echo "alias studio=\"open -a /Applications/Android\ Studio.app\"" >> ~/.zshrc
echo "export GOPATH=$HOME/go" >> ~/.zshrc
source ~/.zshrc
mkdir -p $GOPATH
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
brew cask install homebrew/cask-versions/java8
brew cask install ngrok vmware-fusion atom docker android-sdk android-ndk visual-studio-code skype spotify google-chrome vlc slack dropbox firefox telegram focus goofy signal android-studio spectrum discord google-cloud-sdk
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

## apm's
```
apm install nuclide
```
