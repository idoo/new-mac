# New computer setup

## Xcode, Brew, Casks, Command  Setup
```
# Install Xcode CLI tools (git etc)
xcode-select --install
# Install Homebrew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
# Install Homebrew cask
brew tap caskroom/cask
# Mac AppStore installer
brew install mas
# Install Zsh
brew install zsh
# Install Oh My Zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
# Homebrew Drivers (for sonos)
brew tap homebrew/cask-drivers
```

## Zsh Plugins
```
nano ~/.zshrc
```
- Add 'z' to plugins

## Cask apps
```
# Install cask apps
brew cask install 1password
brew cask install adobe-creative-cloud
brew cask install alfred
brew cask install bartender
brew cask install dash
brew cask install dropbox
brew cask install dropshare
brew cask install firefox
brew cask install focus
brew cask install google-chrome
brew cask install harvest
brew cask install iina
brew cask install iterm2
brew cask install mamp
brew cask install plex-media-player
brew cask install sequel-pro
brew cask install sketch
brew cask install skype
brew cask install slack
brew cask install sonos
brew cask install spectacle
brew cask install spotify
brew cask install tower
brew cask install visual-studio-code
brew cask install xscope
```

## Web Dev
```
# Make 'Sites' folder
mkdir ~/Sites
# Yarn package manager
brew install yarn
# PHP package manager
brew install composer
```

## Wallpaper
- Open Louie Mantia's [Juxtaposition Wallpaper](http://reserve.louie.land/Wallpapers/Juxtaposition/Juxtaposition%20-%20Desktop.jpg) in Safari and use right click > set as wallpaper to

## 1Password
- Open 1Password and sync in via iCloud
- Enable Spotlight and 3rd party app integrations in Preferences > Advanced
- Add Good Work 1Password.com account

## Dropbox
- Open Dropbox, sign into Personal and Work
- Selectively sync just the personal “Sync” folder (do the others later), the Good Work account will do local SmartSync

## Open Alfred
- Activate the Powerpack, licence in 1Password
- Set up syncing under the Advanced tab, the folder is in Dropbox/Sync/Alfred, make sure Dropbox has finished syncing - before doing this
- Remove the default Spotlight shortcut in System Preferences > Keyboard > Shortcuts
- Change shortcut to cmd+space
- Enable clipboard history for all types
- Enable snippets auto expand
- Change theme to macOS Sierra

## Fonts
- Install Dank Mono from Dropbox/Sync

## Chrome
- Open Chrome and sign in to chrisrowenet
- Wait a few minutes for it to sync all settings and extensions etc.

## Trackpad
```
# Enable tap to click for current user and for the login screen
defaults write com.apple.driver.AppleBluetoothMultitouch.trackpad Clicking -bool true
defaults -currentHost write NSGlobalDomain com.apple.mouse.tapBehavior -int 1
defaults write NSGlobalDomain com.apple.mouse.tapBehavior -int 1

```

## System
```
# Expand save panel by default
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool tru
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode2 -bool true
# Save to disk (not to iCloud) by default
defaults write NSGlobalDomain NSDocumentSaveNewDocumentsToCloud -bool fals
# Disable the “Are you sure you want to open this application?” dialog
defaults write com.apple.LaunchServices LSQuarantine -bool fals
# Use Dark menu bar and Dock
defaults write NSGlobalDomain AppleInterfaceStyle -string "Dark
# Show the ~/Library folder
chflags nohidden ~/Librar
```

## Desktop
```
# Show item info near icons
/usr/libexec/PlistBuddy -c "Set :DesktopViewSettings:IconViewSettings:showItemInfo true" ~/Library/Preferences/com.apple.finder.plist
# Show item info to the right of the icons
/usr/libexec/PlistBuddy -c "Set DesktopViewSettings:IconViewSettings:labelOnBottom false" ~/Library/Preferences/com.apple.finder.plist
# Enable snap-to-grid
/usr/libexec/PlistBuddy -c "Set :DesktopViewSettings:IconViewSettings:arrangeBy grid" ~/Library/Preferences/com.apple.finder.plist
# Increase grid spacing
/usr/libexec/PlistBuddy -c "Set :DesktopViewSettings:IconViewSettings:gridSpacing 100" ~/Library/Preferences/com.apple.finder.plist
# Increase the size of icons
/usr/libexec/PlistBuddy -c "Set :DesktopViewSettings:IconViewSettings:iconSize 80" ~/Library/Preferences/com.apple.finder.plist
```

## System Zoom
- Use keyboard shortcuts
- Use scroll gesture ctrl
- Disable smooth images

## Messages
- Check signed in and enable Messages in iCloud

## Dock
- Drag and add “Downloads” to right hand side of Dock
- Disable “Show recent applications in Dock” in System Preferences

```
# Set icon size
defaults write com.apple.dock tilesize -int 80
# Set minimize effect
defaults write com.apple.dock mineffect -string "scale"
# Enable minize into app icon
defaults write com.apple.dock minimize-to-application -bool true
# Remove running app indicators
defaults write com.apple.dock show-process-indicators -bool false
# Remove all icons from dock
defaults write com.apple.dock persistent-apps -array
# Remove icon bounce on launch
defaults write com.apple.dock launchanim -bool false
# Enable autohide
defaults write com.apple.dock autohide -bool true
# Remove autohide delay
defaults write com.apple.dock autohide-delay -float 0
# Reduce show animation duration
defaults write com.apple.dock autohide-time-modifier -float 0.1
```

## Keyboard
```
# Remove alt char popup bubble when holding a key
defaults write -g ApplePressAndHoldEnabled -bool false
# Set key repeat to fastest
defaults write NSGlobalDomain KeyRepeat -int 0
# Set key repeat delay to shortest
defaults write NSGlobalDomain InitialKeyRepeat -int 15
# Disable automatic capitalisation
defaults write NSGlobalDomain NSAutomaticCapitalizationEnabled -bool false
# Enable tabbing through all controls
defaults write NSGlobalDomain AppleKeyboardUIMode -int 3
```

## Disable UI transparency
```
# Remove Menubar transparency
defaults write NSGlobalDomain AppleEnableMenuBarTransparency -bool false
# Remove app transparency
sudo defaults write com.apple.universalaccess reduceTransparency -bool true
```

## Finder
```
# Disable animations
defaults write com.apple.finder DisableAllAnimations -bool true
# Show status bar
defaults write com.apple.finder ShowStatusBar -bool true
# Show path bar
defaults write com.apple.finder ShowPathbar -bool true
# Set default view style
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"
```

## Menubar
```
# Set clock format
defaults write com.apple.menuextra.clock DateFormat -string "EEE MMM d H:mm"
# Show battery percentage
defaults write com.apple.menuextra.battery ShowPercent YES
```

## Hot corner
```
# Use top right to sleep display
defaults write com.apple.dock wvous-tr-corner -int 10
defaults write com.apple.dock wvous-tr-modifier -int 0
```

## Reboot everything to apply settings
```
killall Dock
killall Finder
killall SystemUIServer
killall Terminal
```

## Spectacle
- Run spectacle and disable everything except left/right half, change fullscreen to alt+cmd+up
- Enable “Launch at login”, change to run as a background app in the footer settings

## Internet accounts
- Open “Internet accounts” pref pane and enable relevant services, iCloud keychain should bring them over

## Dropbox
- Disable selective sync (Sync all folders)

## Mail
- Enable contact images in Mail app
- Show most recent messages at the top of conversations

## SSH
- Manually export the 2 key files from 1Password to the desktop
```
cd ~
mkdir .ssh
mv ~/Desktop/id_rsa* ~/.ssh/.
cd .ssh
chmod 600 id_rsa
chmod 644 id_rsa.pub
# Remove ssh key passphrase
ssh-keygen -p
```

## Contacts
- Sort by first name

## git
```
echo ".DS_Store" >> ~/.gitignore_global
git config --global core.excludesfile ~/.gitignore_global
git config --global core.editor nano
```

## Mac AppStore
```
mas install 904280696 ## Things3
mas install 587512244 ## Kaleidoscope 
mas install 406056744 ## Evernote 
mas install 409183694 ## Keynote
mas install 931657367 ## Calcbot 
mas install 597611879 ## Radium 
mas install 411643860 ## DaisyDisk 
mas install 409203825 ## Numbers
mas install 409201541 ## Pages
mas install 413965349 ## Soulver 
mas install 408981434 ## iMovie 
mas install 990588172 ## Gestimer 
mas install 928871589 ## Noizio
mas install 402310348 ## QuickScale 
mas install 1384080005 ## Tweetbot 
mas install 924726344 ## Deliveries 
mas install 414209656 ## Better Rename 9
mas install 975937182 ## Fantastical 2 
```
