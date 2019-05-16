# homebrew-brewfile
My MacBook Brewfile

1) Install [Homebrew](https://brew.sh/)
- /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

2) Sign into the Mac App store, so that `mas` app installs work via Homebrew.

3) Drink from that [Brewfile](https://github.com/jeffpaul/homebrew-brewfile/blob/master/Brewfile) goodness
- brew install mas
- touch Brewfile
- brew bundle install

4) macOS Preferences:
- Bluetooth > Show Bluetooth in menu bar
- Dock > Automatically hide and show the Dock
- Mouse > Point & Click > Secondary click > Click on right side
- Security and Privacy > General > App Store and identified developers
- Security and Privacy > General > Allow your Apple Watch to unlock your Mac
- Security and Privacy > FileVault > On (makes sure SSD is securely encrypted)
- Security and Privacy > Firewall > On
- Software Update > Automatically keep my Mac up to date
- Software Update > Advanced > Install macOS updates
- Software Update > Advanced > Install app updates from the App Store

5) Terminal commands
- Show Library folder: chflags nohidden ~/Library
- Show hidden files: defaults write com.apple.finder AppleShowAllFiles YES
- Keep Homebrew current:
  - touch .bash_profile
  - alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
  - source ~/.bash_profile
  - DAILY CHECK: brewup

6) Manually install:
- [HP Easy Start & HP Firmware Updater](https://support.hp.com/us-en/drivers/selfservice/closure/hp-officejet-pro-8720-all-in-one-printer-series/7902032/model/7902033?sku=M9L74A)
- [Pokemon TGC](https://www.pokemon.com/us/pokemon-tcg/play-online/download/)
- [Sonos](https://www.sonos.com/en-us/support)
- [Sophos](https://home.sophos.com/en-us.aspx)
- [1.1.1.1 DNS](https://1.1.1.1/dns/)

7) Dropbox sync only:
- Downloads
- ZSUZSI

8) Choosy prefs:
- General > Enable Choosy for links
- General > Start Choosy helper at login
- General > (DISABLE) Display Choosy icon in the menu bar
- Browsers > Firefox, Google Chrome, Safari
- Default: Firefox
- Advanced > +
  - Title: Hangouts > Chrome
  - Rule: Web address contains: meet.google.com
  - Rule: Web address contains: google.com/hangouts
  - Always user this browser... Google Chrome
  - Enabled > OK

9) Slack workspaces:
- 10up
- wordpress
- cmssecuritysummit
- poststatus
- thetodogroup

10) Remove from Dock:
- Calendar
- Contacts
- Facetime
- iTunes
- Keynote
- Launchpad
- Mail
- Maps
- News
- Numbers
- Pages
- Photos
- Reminders
- Safari
- Send to Kindle
- Siri
- System Preferences

11) Keep in Dock:
- Finder
- Wavebox
- Slack
- Firefox
- Local by Flywheel
- Amazon Music
- Sonos
- Notes
- zoom.us
- Messages
- Wunderlist
