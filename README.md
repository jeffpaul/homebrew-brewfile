# homebrew-brewfile

> My macOS Brewfile

0. Try Mike McQuaid's Strap tool (and assuming that goes smoothly then skip the next Step 1)
```
git clone https://github.com/MikeMcQuaid/strap
cd strap
bash bin/strap.sh # or bash bin/strap.sh --debug for more debugging output
```

Alternative to running Strap locally: Open https://strap.mikemcquaid.com/ in your web browser.

1. Install [Homebrew](https://brew.sh/)
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

If forced to download Xcode command tools, let's not download ALL of Xcode but the bits we need:
```
touch /tmp/.com.apple.dt.CommandLineTools.installondemand.in-progress;
softwareupdate -i -a
rm /tmp/.com.apple.dt.CommandLineTools.installondemand.in-progress
```

2. Sign into the Mac App store, so that `mas` app installs work via Homebrew.

3. Drink from that [Brewfile](https://github.com/jeffpaul/homebrew-brewfile/blob/main/Brewfile) goodness

~- brew install mas~
~- touch Brewfile~
~- brew bundle install~

- Download [brewfile.sh](https://github.com/jeffpaul/homebrew-brewfile/blob/main/brewfile.sh) to the local user directory
- Run `$ brew bundle` in your terminal and watch the magic happen.

4. macOS Preferences:
- Control Center > Bluetooth > Show in Menu Bar
- Control Center > Menu Bar Only > Clock > Clock Options > Show date: Always
- General > Storage > Empty Trash automatically
- Desktop & Dock > Minimize windows using: Genie Effect
- Desktop & Dock > Minimize windows into application icon
- Desktop & Dock > Automatically hide and show the Dock
- Desktop & Dock > Show recent applications in Dock (DISABLE)
- Displays > Night Shift > Schedule: Sunset to Sunrise
- Network > Firewall > On
- Privacy & Security > Security > Allow applications downloaded from: App Store and identified developers
- Privacy & Security > FileVault > On (makes sure SSD is securely encrypted)
- Trackpad > Point & Click > Secondary click > Click with Two Fingers


- Dropbox files available offline
- Desktop & Screen Saver > Desktop > + > Dropbox > ZSUZSI


- Software Update > Automatically keep my Mac up to date
- Software Update > Advanced > Install macOS updates
- Software Update > Advanced > Install app updates from the App Store
- Sound > Show volume in menu bar

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
- 1.1.1.1 DNS [setup instructions](https://1.1.1.1/dns/)
- [Beardie](https://github.com/Stillness-2/beardie)
- [Blue Sherpa for Blue Yeti mic](https://www.bluedesigns.com/products/sherpa/)
- [Brother iPrint&Scan Push Scan Tool](https://support.brother.com/g/b/downloadlist.aspx?c=us&lang=en&prod=ads2800w_all&os=10052)
- [Logitech HD Pro Webcam C920](https://support.logi.com/hc/en-us/articles/360053977993-Downloads-C922x-Pro-Stream-1080p-Webcam)
- [Pokemon TCG Live](https://tcg.pokemon.com/en-us/tcgl/)
- [Sonos](https://support.sonos.com/s/downloads?language=en_US)
- [Sophos](https://home.sophos.com/en-us.aspx)
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
- Make default browser
- Browsers > Firefox, Google Chrome, Safari
- Advanced > Start Choosy at login
- Advanced > Display Choosy icon in the menu bar (DISABLE)
- Rules > +
  - Title: Google Video > Chrome
  - Any of the following are true
  - Rule: Web address contains: hangouts.google.com
  - Rule: Web address contains: meet.google.com
  - Rule: Web address contains: google.com/hangouts
  - Always use this browser... Google Chrome
  - Enabled > OK
- Rules > +
  - Title: Yomechas
  - Any of the following are true
  - Rule: Web address contains: regsysinc.com
  - Rule: Web address contains: yomechas.org
  - Always use this browser... Safari
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
- Messages
- Zoom
- Firefox
- Microsoft To Do
- Local
- GitHub Desktop
- Amazon Music
- Sonos
- Pocket Casts
- Notes

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
- [Verify git commits](https://gist.github.com/xavierfoucrier/c156027fcc6ae23bcee1204199f177da)

28. Sound Control
- Check for updates automatically
- General > Menu Bar Icon > [speaker]

29. GitHub Desktop
- Advanced > (DISABLE) Help GitHub Desktop improve by submitting usage stats
- Migrate .gitconfig from backup

30. VS Code
- Telemetry: (DISABLE) Enable Telemetry
- Sync settings from GitHub account

31. Messages
- iMessage > (ENABLE) Enable Messages in iCloud

