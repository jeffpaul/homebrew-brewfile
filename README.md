# homebrew-brewfile
My MacBook Brewfile

1) Install [Homebrew](https://brew.sh/)
- /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
2) Drink from that [Brewfile](https://github.com/jeffpaul/homebrew-brewfile/blob/master/Brewfile) goodness
- brew install mas
- touch Brewfile
- brew bundle install
3) macOS Preferences:
- Security and Privacy > FileVault > On (makes sure SSD is securely encrypted)
- Security and Privacy > Firewall > On
- Security and Privacy > General > App Store and identified developers
- Show Library folder: chflags nohidden ~/Library
- Show hidden files: defaults write com.apple.finder AppleShowAllFiles YES
4) Manually install:
- [Pokemon TGC](https://www.pokemon.com/us/pokemon-tcg/play-online/download/)
- [Sonos](https://www.sonos.com/en-us/support)
- [Sophos](https://home.sophos.com/en-us.aspx)
5) Dropbox sync only:
- Downloads
- ZSUZSI
6) Choosy prefs:
- Default: Firefox
- Hangouts > Chrome
- h: meet.google.com/
- h: google.com/hangouts/
7) Keep Homebrew current:
- touch .bash_profile
- alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
- source ~/.bash_profile
- DAILY CHECK: brewup
