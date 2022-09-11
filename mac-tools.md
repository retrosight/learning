# Mac Tools

> A comprehensive list of great MacOS software: https://github.com/jaywcjlove/awesome-mac

## Developer

* [Visual Studio Code](https://code.visualstudio.com)
* Fonts
  * [Source Code Pro](https://fonts.google.com/specimen/Source+Code+Pro)
  * [Victor Mono](https://rubjo.github.io/victor-mono/)
    * `brew tap homebrew/cask-fonts`
    * `brew install --cask font-victor-mono`
* [Kaleidoscope](http://www.kaleidoscopeapp.com)
* [Homebrew](https://brew.sh)
  * `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
* [iTerm2](http://www.iterm2.com)
  * `brew install --cask iterm2`
* [Zsh](https://medium.com/swlh/power-up-your-terminal-using-oh-my-zsh-iterm2-c5a03f73a9fb)
  * `brew install zsh`
  * `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
* Git
  * `brew install git`
  * `brew upgrade git`
  * `export PATH=/usr/local/bin:$PATH`
* [cUrl](https://curl.haxx.se)
  * `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" 2> /dev/null`
  * `brew install curl`
* [Authy](https://authy.com)

---

* [Web Sequence Diagrams](https://www.websequencediagrams.com)
* [Brackets](http://brackets.io)
* [Sublime Text](http://www.sublimetext.com/3)
* [StackEdit](https://stackedit.io/app#)
* [Eclipse](https://www.eclipse.org)
* [Xcode](https://developer.apple.com/xcode/)
* [NodeJS](https://nodejs.org/en/)
* [Node Package Manager (NPM)](https://www.npmjs.com)
* [Electron](http://electron.atom.io)
* [Git + GitHub](https://help.github.com/en/articles/set-up-git)
* [GitHub Desktop](https://desktop.github.com)
* [Docker](https://www.docker.com)
* [Parallels](http://www.parallels.com)
* [Vagrant](https://www.vagrantup.com)
* [MongoDB](https://www.mongodb.com)

## Productivity

* [MindNode](http://mindnode.com)
* [Slack](https://slack.com)
* [Brave](https://brave.com)
* [Chrome](https://www.google.com/chrome/)
* [BetterTouchTool, BetterSnapTool, BTT Remote, KeyboardCleanTool](https://folivora.ai)
* [Caffeine](https://www.intelliscapesolutions.com/apps/caffeine) - Current fave.
* [Trello](https://trello.com)
* Add spaces to MacOS Dock
  * `defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'; killall Dock`
* Show hidden files and folders
  * `defaults write com.apple.finder AppleShowAllFiles -bool TRUE;killall Finder`
* Change the location for screenshots
  * `defaults write com.apple.screencapture location /Users/charlie/Downloads;killall SystemUIServer`
* [RDM](https://github.com/avibrazil/RDM) - This is a tool that lets you use MacBook Pro Retina's highest and unsupported resolutions.

## Creativity

* [Audacity](http://www.audacityteam.org)
* [FFMPeg Library](https://www.ffmpeg.org)
  * `brew install ffmpeg`
  * Static for Audacity: https://lame.buanzo.org/#lameosx64bitdl
* [Handbrake](https://handbrake.fr)
  * `brew install libdvdcss`
* [YouTube Downloader](https://youtube-dl.org)
  * `brew install youtube-dl`
* [Gravit Designer](https://designer.io)
