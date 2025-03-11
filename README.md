# homebrew-brewfile

> My macOS Brewfile

0. Before beginning, consider exporting existing macOS Preferences (whether you use to import later or keep as reference, it can't hurt):
```
# Create a backup directory
mkdir -p ~/macos_prefs_backup

# Export all user defaults
defaults read > ~/macos_prefs_backup/macos_preferences_backup.plist

# Finder Preferences
defaults read com.apple.finder > ~/macos_prefs_backup/finder_prefs.plist

# Dock Preferences
defaults read com.apple.dock > ~/macos_prefs_backup/dock_prefs.plist

# Global System Preferences (Trackpad, Keyboard, etc.)
defaults read NSGlobalDomain > ~/macos_prefs_backup/global_prefs.plist

# Screenshot Preferences
defaults read com.apple.screencapture > ~/macos_prefs_backup/screencapture_prefs.plist

# Terminal Preferences
defaults read com.apple.terminal > ~/macos_prefs_backup/terminal_prefs.plist

# Mission Control & Spaces
defaults read com.apple.spaces > ~/macos_prefs_backup/mission_control_prefs.plist

# Hot Corners
defaults read com.apple.dock wvous-tl-corner > ~/macos_prefs_backup/hotcorners_tl.txt
defaults read com.apple.dock wvous-tr-corner > ~/macos_prefs_backup/hotcorners_tr.txt
defaults read com.apple.dock wvous-bl-corner > ~/macos_prefs_backup/hotcorners_bl.txt
defaults read com.apple.dock wvous-br-corner > ~/macos_prefs_backup/hotcorners_br.txt

# Archive everything for easy transfer
tar -czvf ~/macos_prefs_backup.tar.gz ~/macos_prefs_backup/

echo "✅ macOS preferences backed up to ~/macos_prefs_backup.tar.gz"
```
Save `macos_prefs_backup.tar.gz` to an external drive or cloud storage.

1. Install [Homebrew](https://brew.sh/)
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

If forced to download Xcode command tools, let's not download ALL of Xcode but the bits we need:
```
xcode-select --install
```

2. Sign into the Mac App store, so that `mas` app installs work via Homebrew.

3. Drink from that [Brewfile](https://github.com/jeffpaul/homebrew-brewfile/blob/main/Brewfile) goodness
```
curl -o ~/Brewfile https://raw.githubusercontent.com/jeffpaul/homebrew-brewfile/main/Brewfile
```

Then...
```
brew bundle --file=~/Brewfile
```

- Restore SSH Keys & Configs
From SSH key backup:
```
mkdir -p ~/.ssh && cp /path/to/backup/.ssh/* ~/.ssh/
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
ssh-add ~/.ssh/id_rsa
```

Restoring dotfiles:
```
cp /path/to/backup/.zshrc ~/
cp /path/to/backup/.gitconfig ~/
source ~/.zshrc
```

- Validate installed files
```
brew list
```
If any apps are missing, re-run: 
```
brew bundle --file=~/Brewfile
```

- If you want to import macOS Preferences:
```
# Unpack the backup
tar -xzvf ~/macos_prefs_backup.tar.gz -C ~

# Restore system-wide preferences
defaults import NSGlobalDomain ~/macos_prefs_backup/global_prefs.plist

# Restore Finder settings
defaults import com.apple.finder ~/macos_prefs_backup/finder_prefs.plist
killall Finder

# Restore Dock settings
defaults import com.apple.dock ~/macos_prefs_backup/dock_prefs.plist
killall Dock

# Restore Screenshot preferences
defaults import com.apple.screencapture ~/macos_prefs_backup/screencapture_prefs.plist
killall SystemUIServer

# Restore Terminal preferences
defaults import com.apple.terminal ~/macos_prefs_backup/terminal_prefs.plist

# Restore Mission Control & Spaces
defaults import com.apple.spaces ~/macos_prefs_backup/mission_control_prefs.plist

# Restore Hot Corners
defaults write com.apple.dock wvous-tl-corner -int $(cat ~/macos_prefs_backup/hotcorners_tl.txt)
defaults write com.apple.dock wvous-tr-corner -int $(cat ~/macos_prefs_backup/hotcorners_tr.txt)
defaults write com.apple.dock wvous-bl-corner -int $(cat ~/macos_prefs_backup/hotcorners_bl.txt)
defaults write com.apple.dock wvous-br-corner -int $(cat ~/macos_prefs_backup/hotcorners_br.txt)
killall Dock

# Restart to apply all settings
echo "✅ macOS preferences restored! Restarting now..."
sudo reboot
```

4. macOS Preferences:
- Control Center > Bluetooth > Show in Menu Bar
- Control Center > Menu Bar Only > Clock > Clock Options > Show date: Always
- Control Center > Sound > Don't Show in Menu Bar
- General > Software Update > Automatic updates > (!) > Install macOS updates
- General > Software Update > Automatic updates > (!) > Install application updates from the App Store

- Desktop & Dock > Minimize windows using: Genie Effect
- Desktop & Dock > Minimize windows into application icon (ENABLE)
- Desktop & Dock > Automatically hide and show the Dock (ENABLE)
- Desktop & Dock > Show suggested and recent apps in Dock (DISABLE)
- Desktop & Dock > Windows > Drag windows to screen edges to tile (DISABLE)
- Desktop & Dock > Windows > Drag windows to menu bar to fill screen (DISABLE)
- Displays > Night Shift > Schedule: Sunset to Sunrise
- Network > Firewall (ENABLE)
- Privacy & Security > Security > Allow applications downloaded from: App Store & Known Developers
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
Ensure a DAILY CHECK to run: `brewup`.

6. Dropbox settings:
- Sign in with Dropbox
- Select folders to sync to this Mac > Select folders:
  - Downloads
  - Family photos - 2015
  - Family photos - 2019
  - Family photos - 2021
  - Music > Amazon Music
  - Music > iTunes > iTunes Media > Music
- General > Dropbox badge > Never show
- Sync > Default sync state for new files: Online-only
- macOS Settings > Screen Saver > Other > Photos > Style: Vintage Prints > Options > Choose folder: Dropbox > Family photos - 2021

7. Keybase settings:
- Files > Enable Finder Integration

8. Chrome settings:
- Sign in to Chrome (work & personal)
- Appearance > Show warning before quitting with commandQ (DISABLE)
- Downloads: Dropbox/Downloads

9. Firefox settings:
- SIGN IN
- General > Files and Applications > Downloads > Save files to: Dropbox/Downloads
- Search > Default Search Engine: DuckDuckGo
- Privacy & Security > Passwords > DISABLE ALL
- Privacy & Security > Autofill > DISABLE ALL
- Privacy & Security > Firefox Data Collection and Use > DISABLE ALL
- Privacy & Security > History > Firefox will: Use custom settings for history > (DISABLE) Remember search and form history
- about:config > dom.forms.selectSearch <> `true`

10. Safari settings:
- General > File download location: Dropbox/Downloads

11. Choosy prefs:
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

```
12. Manually install:
~ - 1.1.1.1 DNS [setup instructions](https://1.1.1.1/dns/) ~
~ - [Beardie](https://github.com/Stillness-2/beardie) ~
~ - [Blue Sherpa for Blue Yeti mic](https://www.bluedesigns.com/products/sherpa/) & [Logitech G Hub](https://www.logitechg.com/en-us/innovation/g-hub.html) ~
~ - [Brother iPrint&Scan Push Scan Tool](https://support.brother.com/g/b/downloadlist.aspx?c=us&lang=en&prod=ads2800w_all&os=10072) ~
~ - [Logitech HD Pro Webcam C920](https://support.logi.com/hc/en-us/articles/360053977993-Downloads-C922x-Pro-Stream-1080p-Webcam) ~
~ - [Sonos](https://support.sonos.com/s/downloads?language=en_US) ~
```

13. Amazon Music preferences:
- Music Management > Download Location > /Users/jeffpaul/Dropbox/Music/Amazon Music
- System Preferences > Show notifications for track playing (DISABLE)

14. Bartender preferences:
- General > Startup: Launch Bartender at login
- Apply License Key

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
- Activate License
- Dock Window
- General > Start at login
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
- Appearance > Menu Bar Icon: <speaker>
- Options > Launch Sound Control at startup (ENABLE)
- Device Order > Input > Yeti then C922

23. VS Code
- Sync to and from other devices > Enable Settings Sync > Sign in with GitHub

24. Wavebox settings:
- Show warning before quitting with commandQ (DISABLE)

25. Zoom preferences:
- SIGN IN
- General > Ask me to confirm when I leave a meeting (DISABLE)
- General > Add Zoom to macOS menu bar (DISABLE)
- General > Activate the following emojis based on hand gesture recognition (ENABLE)
- Video > Camera > HD
- Video > Always display participant name on their videos (DISABLE)
- Audio > Automatically join computer audio when joining (ENABLE)
- Background & effects > Adjust for low light: Auto (ENABLE)
- Recording > Local Recording > Store my recordings at: Dropbox/Downloads

26. GPG Keychain
- Import
- [Verify git commits](https://gist.github.com/xavierfoucrier/c156027fcc6ae23bcee1204199f177da)

27. GitHub Desktop settings:
- SIGN IN
- Git > Email: <personal email>
- Git > Default branch name for new repositories > Other: trunk
- Advanced > Usage > Help GitHub Desktop improve by submitting usage stats (DISABLE)
- Migrate .gitconfig from backup

28. Keep in Dock:
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
- VS Code
- Cursor
- Amazon Music
- Pocket Casts
- Notes

29. Finder settings:
- General > Show these items on the desktop: External disks (DISABLE)
- General > Show these items on the desktop: CDs, DVDs, and iPods (DISABLE)
- General > New Finder windows show: Dropbox/Downloads
- Advanced > Show all filename extensions (ENABLE)
- Advanced > Show warning before removing from iCloud Drive (DISABLE)
- Advanced > When performaing a search > Search the Current Folder
- Advanced > Remove items from the Trash after 30 days (ENABLE)

30. Finder sidebar:
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

31. Load fonts
- open Font Book, import from fonts

32. Papriaka
- Login & Sync

33. FINALLY... Run brew doctor to ensure everything is set up correctly: 
```
brew doctor
```
Restart Mac for a fresh start!
