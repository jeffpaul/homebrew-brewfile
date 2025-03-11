# homebrew-brewfile

> My macOS Brewfile

After running through the following setup, you can use `brew cu` to upgrade all Mac apps installed via [Brew](https://brew.sh/).  You can also dump your loal Brewfil of current brew/cask/mas entries via `brew bundle bump --file=~/.private/Brewfil`.  To remove an app you can use `brew cask zap <caskname>` to remove the app and preferences, caches, updaters, etc.

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

- Download [Brewfile](https://github.com/jeffpaul/homebrew-brewfile/blob/main/Brewfile) to the local user directory

~- brew install mas~

~- touch Brewfile~

- brew bundle install

- Run `$ brew bundle` in your terminal and watch the magic happen.

4. macOS Preferences:
- Control Center > Bluetooth > Show in Menu Bar
- Control Center > Menu Bar Only > Clock > Clock Options > Show date: Always
- Control Center > Sound > Always Show in Menu Bar
- General > Software Update > Automatic updates > (!) > Install macOS updates
- General > Software Update > Automatic updates > (!) > Install application updates from the App Store
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

5. Terminal commands:
- Show Library folder: chflags nohidden ~/Library
- Show hidden files: defaults write com.apple.finder AppleShowAllFiles YES
- echo 'export PATH="/usr/local/sbin:$PATH"' >> ~/.zshrc
- Keep Homebrew current:
  - touch .bash_profile
  - alias brewup='brew update; brew upgrade; brew cleanup; brew doctor'
  - source ~/.bash_profile
  - DAILY CHECK: brewup

6. Chrome settings:
- Appearance > Show warning before quitting with commandQ (DISABLE)
- Downloads: Dropbox/Downloads

7. Firefox settings:
- SIGN IN
- General > Files and Applications > Downloads > Save files to: Dropbox/Downloads
- Search > Default Search Engine: DuckDuckGo
- Privacy & Security > Logins and Passwords > DISABLE ALL
- Privacy & Security > Firefox Data Collection and Use > DISABLE ALL
- Privacy & Security > Forms and Autofill > DISABLE ALL
- Privacy & Security > History > Firefox will: Use custom settings for history > (DISABLE) Remember search and form history
- about:config > (ENABLE) dom.forms.selectSearch

8. Safari settings:
- General > File download location: Dropbox/Downloads

9. Choosy prefs:
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

10. Manually install:
- 1.1.1.1 DNS [setup instructions](https://1.1.1.1/dns/)
- [Beardie](https://github.com/Stillness-2/beardie)
- [Blue Sherpa for Blue Yeti mic](https://www.bluedesigns.com/products/sherpa/) & [Logitech G Hub](https://www.logitechg.com/en-us/innovation/g-hub.html)
- [Brother iPrint&Scan Push Scan Tool](https://support.brother.com/g/b/downloadlist.aspx?c=us&lang=en&prod=ads2800w_all&os=10072)
- [Logitech HD Pro Webcam C920](https://support.logi.com/hc/en-us/articles/360053977993-Downloads-C922x-Pro-Stream-1080p-Webcam)
- [Pokemon TCG Live](https://tcg.pokemon.com/en-us/tcgl/)
- [Sonos](https://support.sonos.com/s/downloads?language=en_US)

11. Amazon Music preferences:
- Music Management > Download Location > /Users/jeffpaul/Dropbox/Music/Amazon Music
- System Preferences > Show notifications for track playing (DISABLE)

12. Bartender preferences:
- General > Startup: Launch Bartender at login

13. Beardie settings: (perhaps migrated to Sound Control?)
- Launch at login
- Enable Browser Extensions

14. Dropbox settings:
- General > Dropbox badge > Never show
- Sync > Storage of new files: Online-only
- Select folders to sync to this Mac > Select folders:
  - Downloads
  - Family photos - 2015
  - Family photos - 2019
  - Family photos - 2021
  - Music > Amazon Music
  - Music > iTunes > iTunes Media > Music
- macOS Settings > Screen Saver > Vintage Prints > Options > Choose folder: Dropbox > Family photos - 2021

```
15. HP Easy Scan preferences
- Scan to Computer > Save as Editable Text (OCR) > Scan To: Dropbox/Downloads
- Scan to Computer > Save as JPEG > Scan To: Dropbox/Downloads
- Scan to Computer > Save as PDF > Scan To: Dropbox/Downloads
```

16. Local preferences:
- LOG IN

17. Mail preferences:
- General > Downloads folder: Dropbox/Downloads

18. Memory Clean 3 preferences:
- Dock Window
- General > Hide window at startup
- App Management > Notify me when apps become inactive (DISABLE)
- Advanced > Threshold level: 2000 MB
- Advanced > Auto clean

19. Messages settings:
- iMessage > Enable Messages in iCloud
- iMessage > Sync Now
- Launch Contacts app > Settings > Accounts (+) > Google > <Gmail account> > Select Contacts only

20. Music settings:
- Files > Music Media folder location: /Users/jeffpaul/Dropbox/Music/iTunes/iTunes Media/Music

21. Slack settings
- Workspaces:
  - 10up
  - wordpress
  - woocommerce
  - newspack
  - poststatus
  - thewpcc
  - thetodogroup
  - cmssecuritysummit
  - indieweb
  - gatherpress
- Settings > Advanced > Download Location: Dropbox/Downloads

22. Sound Control preferences:
- Check for updates automatically
- General > Menu Bar Icon: <speaker>
- Priority Devices > Input > Yeti then C922

23. VS Code
- Sync to and from other devices > Enable Settings Sync > Sign in with GitHub

24. Wavebox settings:
- Show warning before quitting with commandQ (DISABLE)

25. Zoom preferences:
- SIGN IN
- General > Ask me to confirm when I leave a meeting (DISABLE)
- General > Add Zoom to macOS menu bar (DISABLE
- General > Activate the following emojis based on hand gesture recognition
- Video > Camera > HD
- Video > My Video > Adjust for low light: Auto
- Video > Always display participant name on their videos
- Audio > Automatically join computer audio when joining a meeting
- Recording > Local Recording > Store my recordings at: Dropbox/Downloads

26. Keybase settings:
- Files > Enable Finder Integration

27. GPG Keychain
- Import
- [Verify git commits](https://gist.github.com/xavierfoucrier/c156027fcc6ae23bcee1204199f177da)

28. GitHub Desktop settings:
- SIGN IN
- Git > Email: <personal email>
- Git > Default branch name for new repositories > Other: trunk
- Advanced > Usage > Help GitHub Desktop improve by submitting usage stats (DISABLE)
- Migrate .gitconfig from backup

29. Keep in Dock:
- Finder
- Wavebox
- Slack
- Messages
- Signal
- Firefox
- Google Chrome
- Google Meet
- Local
- GitHub Desktop
- Cursor
- Amazon Music
- Pocket Casts
- Notes

30. Finder settings:
- General > Show these items on the desktop: External disks (DISABLE)
- General > Show these items on the desktop: CDs, DVDs, and iPods (DISABLE)
- General > New Finder windows show: Dropbox/Downloads
- Advanced > Show all filename extensions
- Advanced > Show warning before removing from iCloud Drive (DISABLE)
- Advanced > When performaing a search > Search the Current Folder

31. Finder sidebar:
- (KEEP) AirDrop
- (KEEP) Appications
- (KEEP) Desktop
- (REMOVE) Documents
- (REMOVE) Downloads
- (ADD) Dropbox/Downloads
- (KEEP) Dropbox
- (ADD) jeffpaul
- (KEEP) Keybase
- (KEEP) Recents

32. Load fonts
- open Font Book, import from fonts
