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
brew install zsh zsh-completions
chsh -s /bin/zsh
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
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
brew cask install virtualbox
brew cask install genymotion
brew cask install java
brew cask install android-studio
brew cask install microsoft-office365
brew cask install google-drive
brew cask install focus
brew cask install atom
brew cask install dashlane
```

