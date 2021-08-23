# homebrew-brewfile
My MacBook Brewfile

1. Install [Homebrew](https://brew.sh/)
- /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

2. Sign into the Mac App store, so that `mas` app installs work via Homebrew.

3. Drink from that [Brewfile](https://github.com/jeffpaul/homebrew-brewfile/blob/main/Brewfile) goodness
- brew install mas
- touch Brewfile
- brew bundle install

4. macOS Preferences:
- Bluetooth > Show Bluetooth in menu bar
- Dock & Menu Bar > Clock > Show date
- Desktop & Screen Saver > Desktop > + > Dropbox > ZSUZSI
- Dock > Minimize windows into application icon
- Dock > Automatically hide and show the Dock
- Dock > (DISABLE) Show recent applications in Dock
- Mouse > Point & Click > Secondary click > Click on right side
- Security and Privacy > General > App Store and identified developers
- Security and Privacy > FileVault > On (makes sure SSD is securely encrypted)
- Security and Privacy > Firewall > On
- Software Update > Automatically keep my Mac up to date
- Software Update > Advanced > Install macOS updates
- Software Update > Advanced > Install app updates from the App Store
- Sound > Show volume in menu bar
- Displays > Night Shift > Schedule: Sunset to Sunrise

5. Terminal commands
- Show Library folder: chflags nohidden ~/Library
- Show hidden files: defaults write com.apple.finder AppleShowAllFiles YES
- echo 'export PATH="/usr/local/sbin:$PATH"' >> ~/.zshrc
- Keep Homebrew current:
  - touch .bash_profile
  - alias brewup='brew update; brew upgrade; brew cleanup; brew doctor'
  - source ~/.bash_profile
  - DAILY CHECK: brewup

6. Manually install:
- [Google Drive Filestream](https://www.google.com/drive/download/)
- [Pokemon TGC](https://www.pokemon.com/us/pokemon-tcg/play-online/download/)
- [Sonos](https://www.sonos.com/en-us/support)
- [Sophos](https://home.sophos.com/en-us.aspx)
- 1.1.1.1 DNS [setup instructions](https://1.1.1.1/dns/)
- [Logitech HD Pro Webcam C920](https://support.logitech.com/en_us/product/hd-pro-webcam-c920/downloads#)
- [Blue Sherpa for Blue Yeti mic](https://www.bluedesigns.com/products/sherpa/)
- [Brother iPrint&Scan Push Scan Tool](https://support.brother.com/g/b/downloadlist.aspx?c=us&lang=en&prod=ads2800w_all&os=10052)
- [Sound Control](https://staticz.com/soundcontrol/)

7. Dropbox
- General > Dropbox badge > Never show
- Sync > Save hard drive space automatically > On
- Selective Sync > Choose folders:
  - Downloads
  - Family photos - 2015
  - Family photos - 2019
  - GitHub
  - GitLab
  - Music > Amazon Music
  - Music > iTunes > iTunes Media > Music

8. Choosy prefs:
- Browsers > Firefox, Google Chrome, Safari
- Advanced > Start Choosy at login
- Advanced > (DISABLE) Display Choosy icon in the menu bar
- Rules > +
  - Title: Hangouts > Chrome
  - Rule: Web address contains: meet.google.com
  - Rule: Web address contains: google.com/hangouts
  - Always user this browser... Google Chrome
  - Enabled > OK
- Rules > (EDIT) Default behavior
  - Always user this browser... Firefox
  - Enabled > OK
- About > Register

9. Slack settings
- Workspaces:
  - 10up
  - wordpress
  - woocommerce
  - newspack
  - poststatus
  - cmssecuritysummit
  - thetodogroup
  - indieweb
- Advanced > Download Location: Dropbox/Downloads

10. Remove from Dock:
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

11. Keep in Dock:
- Finder
- Wavebox
- Slack
- Firefox
- Local
- Amazon Music
- Sonos
- Pocket Casts
- Notes
- Zoom
- Messages

12. Bartender preferences:
- Menu Items > AirPort - Wi-Fi > Menu bar item should > Hide
- Menu Items > Airplay Displays > Menu bar item should > Hide
- Menu Items > Dropbox > Menu bar item should > Hide
- Menu Items > Sophos Home > Menu bar item should > Hide
- General > Startup: Launch Bartender at login

13. Memory Clean 3 preferences:
- Dock Window
- General > Hide window at startup
- App Management > (DISABLE) Notify me when apps become inactive
- Advanced > Threshold level: 2000 MB
- Advanced > Auto clean

14. Music preferences:
- Files > Music Media folder location: /Users/jeffpaul/Dropbox/Music

15. Safari preferences:
- General > File download location: Dropbox/Downloads

16. Firefox preferences:
- General > Files and Applications > Downloads > Save files to: Dropbox/Downloads
- Search > Default Search Engine: DuckDuckGo
- about:config > (ENABLE) dom.forms.selectSearch
- Privacy & Security > Use custom settings for history > (DISABLE) Remember search and form history

17. Chrome preferences:
- Advanced > Downloads > Location: Dropbox/Downloads
- (DISABLE) Warn before quitting

18. Mail preferences:
- General > Downloads folder: Dropbox/Downloads

19. Keybase settings
- Files > Enable Finder Integration

20. Local settings
- Local site path: Dropbox/Local Sites

21. Finder sidebar
- (KEEP) AirDrop
- (KEEP) Appications
- (KEEP) Desktop
- (REMOVE) Documents
- (REMOVE) Downloads
- (ADD) Dropbox/Downloads
- (KEEP) Dropbox
- (ADD) jeffpaul
- (KEEP) Keybase
- (ADD) Dropbox/Local Sites
- (KEEP) Recents

22. Finder preferences
- General > Show these items on the desktop: (DISABLE) External disks
- General > Show these items on the desktop: (DISABLE) CDs, DVDs, and iPods
- General > New Finder windows show: Dropbox/Downloads
- Advanced > (ENABLE) Show all filename extensions
- Advanced > (DISALBE) Show warning before removing from iCloud Drive
- Advanced > When performaing a search > Seath the Current Folder

23. Zoom preferences
- General > (DISABLE) Ask me to confirm when I leave a meeting
- Video > Camera > HD
- Video > Meetings > Always display participant name on their videos
- Recording > Local Recording > Store my recordings at: Dropbox/Downloads

24. Amazon Music preferences
- Music Management > Download Location > /Users/jeffpaul/Dropbox/Music/Amazon Music
- (DISABLE) Advanced > Launch automatically on computer startup
- System Preferences > (DISABLE) Show notifications for track playing

25. HP Easy Scan preferences
- Scan to Computer > Save as Editable Text (OCR) > Scan To: Dropbox/Downloads
- Scan to Computer > Save as JPEG > Scan To: Dropbox/Downloads
- Scan to Computer > Save as PDF > Scan To: Dropbox/Downloads

26. Wavebox
- (DISABLE) Warn Before Quitting

27. GPG Keychain
- Import

28. Sound Control
- Check for updates automatically
- General > Menu Bar Icon > [speaker]

29. GitHub Desktop
- Advanced > (DISABLE) Help GitHub Desktop improve by submitting usage stats
- Migrate .gitconfig from backup

30. VS Code
- Telemetry: (DISABLE) Enable Telemetry

31. Messages
- iMessage > (ENABLE) Enable Messages in iCloud

