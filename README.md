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
- Date & Time > Clock > Show date
- Desktop & Screen Saver > Desktop > + > Dropbox > ZSUZSI
- Dock > Minimize windows into application icon
- Dock > Automatically hide and show the Dock
- Dock > (DISABLE) Show recent applications in Dock
- Mouse > Point & Click > Secondary click > Click on right side
- Security and Privacy > General > App Store and identified developers
- Security and Privacy > General > Allow your Apple Watch to unlock your Mac
- Security and Privacy > FileVault > On (makes sure SSD is securely encrypted)
- Security and Privacy > Firewall > On
- Software Update > Automatically keep my Mac up to date
- Software Update > Advanced > Install macOS updates
- Software Update > Advanced > Install app updates from the App Store
- Desktop > Use Stacks

5) Terminal commands
- Show Library folder: chflags nohidden ~/Library
- Show hidden files: defaults write com.apple.finder AppleShowAllFiles YES
- Keep Homebrew current:
  - touch .bash_profile
  - alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
  - source ~/.bash_profile
  - DAILY CHECK: brewup

6) Manually install:
- [Google Drive Filestream](https://www.google.com/drive/download/)
- [HP Easy Start & HP Firmware Updater](https://support.hp.com/us-en/drivers/selfservice/closure/hp-officejet-pro-8720-all-in-one-printer-series/7902032/model/7902033?sku=M9L74A)
- [Pokemon TGC](https://www.pokemon.com/us/pokemon-tcg/play-online/download/)
- [Sonos](https://www.sonos.com/en-us/support)
- [Sophos](https://home.sophos.com/en-us.aspx)
- [1.1.1.1 DNS](https://1.1.1.1/dns/)

7) Dropbox sync only:
- Downloads
- Music > iTunes > iTunes Media > Music
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
- Terminal

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

12) Bartender preferences:
- Menu Items > AirPort - Wi-Fi > Menu bar item should > Hide
- Menu Items > Airplay Displays > Menu bar item should > Hide
- Menu Items > BeardedSpice > Menu bar item should > Hide
- Menu Items > Dropbox > Menu bar item should > Hide
- Menu Items > Sophos Home > Menu bar item should > Hide
- Menu Items > Siri > Menu bar item should > Hide
- Menu Items > WunderlistHelper > Menu bar item should > Hide
- General > Open Bartender at login

13) Wunderlist preferences:
- General > Open Wunderlist at startup

14) Memory Clean 3 preferences:
- Dock Window
- General > Hide window at startup
- App Management > (DISABLE) Notify me when apps become inactive
- Advanced > Threshold level: 2000 MB
- Advanced > Auto clean

15) iTunes preferences:
- Advanced > iTunes Media folder location: /Users/jeffpaul/Dropbox/Music/iTunes/iTunes Media/Music

16) Safari preferences:
- General > File download location: Dropbox/Downloads

17 ) Firefox preferences:
- General > Files and Applications > Downloads > Save files to: Dropbox/Downloads
- Search > Default Search Engine: DuckDuckGo

18 ) Chrome preferences:
- Advanced > Downloads > Location: Dropbox/Downloads

19) Mail preferences:
- General > Downloads folder: Dropbox/Downloads

20) Keybase settings
- Files > Enable Keybase in Finder

21) Local by Flywheel settings
- Local site path: Dropbox/Local Sites

22) Finder sidebar
- (KEEP) AirDrop
- (KEEP) Appications
- Downloads > Remove from Sidebar
- Dropbox/Downloads > Add to Sidebar
- (KEEP) Dropbox
- Dropbox/GitHub > Add to Sidebar
- Google Drive > Add to Sidebar
- jeffpaul > Add to Sidebar
- (KEEP) Keybase
- Dropbox/Local Sites > Add to Sidebar
- (KEEP) Recents

23) Finder preferences
- General > Show these items on the desktop: (DISABLE) External disks
- General > Show these items on the desktop: (DISABLE) CDs, DVDs, and iPods
- General > New Finder windows show: Dropbox/Downloads
- Advanced > Show all filename extensions

24) zoom.us preferences
- General > (DISABLE) Prompt a confirmation before leaving a meeting
- Video > My Video > Enable HD
- Video > Meetings > Always display participant name on their videos
