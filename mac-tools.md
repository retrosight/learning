# Mac Tools

> A comprehensive list of great MacOS software: https://github.com/jaywcjlove/awesome-mac

* [Atom](https://atom.io)
  * Fonts
    * [Source Code Pro](https://fonts.google.com/specimen/Source+Code+Pro)
    * [Victor Mono](https://rubjo.github.io/victor-mono/)
      * `brew tap homebrew/cask-fonts`
      * `brew install --cask font-victor-mono`
  * Editor Settings
    * Scroll Past End = Enable
    * Soft Tabs = Enable
  * Packages
    * [script](https://atom.io/packages/script)
      * `apm install script`
    * [predawn syntax](https://atom.io/themes/predawn-syntax)
      * `apm install predawn-syntax`
    * [file-icons](https://atom.io/packages/file-icons)
      * `apm install --production file-icons`
    * [minimap](https://atom.io/packages/minimap)
      * `apm install minimap`
  * Packages: Language Specific
    * [python-autopep8](https://atom.io/packages/python-autopep8)
      * `pip install autopep8`
      * `apm install python-autopep8`
    * [linter-flake8](https://atom.io/packages/linter-flake8)
       * `pip install flake8`
       * `apm install linter-flake8`
    * Set python3 as default for run.
      * Preferences > Packages > Script > Settings > View Code
      * Edit /lib/grammars/python.js
        * export const Python > Selection Based > `command: "python3"`
        * export const Python > File Based > `command: "python3"`
    * (Optional) [autocomplete-python](https://atom.io/packages/autocomplete-python)
  * Shortcuts
    * Run: `CMD` + `i`
    * Run with profile = `CMD` + `SHIFT` + `k`
    * Configure Run Options: `CMD` + `SHIFT` + `i`
    * Run Atom Package: `CMD` + `SHIFT` + `p`
* [Kaleidoscope](http://www.kaleidoscopeapp.com)
* [cUrl](https://curl.haxx.se)
* [Homebrew](https://brew.sh)
  * `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
* [iTerm2](http://www.iterm2.com)
  * `brew cask install iterm2`
* [Zsh](https://medium.com/swlh/power-up-your-terminal-using-oh-my-zsh-iterm2-c5a03f73a9fb)
  * `brew install zsh`
  * `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
* [MindNode](http://mindnode.com)
* [Slack](https://slack.com)
* [Audacity](http://www.audacityteam.org)
* [FFMPeg Library](https://www.ffmpeg.org)
  * `brew install ffmpeg`
  * Static for Audacity: https://lame.buanzo.org/#lameosx64bitdl
* [Handbrake](https://handbrake.fr)
  * `brew install libdvdcss`
* [YouTube Downloader](https://formulae.brew.sh/formula/youtube-dl)
  * `brew install youtube-dl`
* [Brave](https://brave.com)
* [Chrome](https://www.google.com/chrome/)
* [BetterTouchTool, BetterSnapTool, BTT Remote, KeyboardCleanTool](https://folivora.ai)
* [Authy](https://authy.com)
* [Caffeine](https://www.intelliscapesolutions.com/apps/caffeine) - Current fave.
* [Add spaces to MacOS Dock](https://www.imore.com/add-space-your-mac-dock)
  * `defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'; killall Dock`
---
* [Brackets](http://brackets.io)
* [Sublime Text](http://www.sublimetext.com/3)
* [StackEdit](https://stackedit.io/app#)
* [Eclipse](https://www.eclipse.org)
* [Espresso](https://espressoapp.com)
* [Xcode](https://developer.apple.com/xcode/)
* [Insomnia](https://insomnia.rest)
* [NodeJS](https://nodejs.org/en/)
* [Node Package Manager (NPM)](https://www.npmjs.com)
* [Electron](http://electron.atom.io)
* [Git](https://help.github.com/en/articles/set-up-git)
* [GitHub Desktop](https://desktop.github.com)
* [Docker](https://www.docker.com)
* [Parallels](http://www.parallels.com)
* [Vagrant](https://www.vagrantup.com)
* [MongoDB](https://www.mongodb.com)
* [Gravit Designer](https://designer.io)
* [OmniGraffle](https://www.omnigroup.com/omnigraffle)
* [Airmail](http://airmailapp.com)
* [Spark](https://sparkmailapp.com)
* [SizeUp](http://www.irradiatedsoftware.com/sizeup/)
* [Trello](https://trello.com)
* [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator)
* [InsomniaX](https://www.macupdate.com/app/mac/22211/insomniax)
* [Web Sequence Diagrams](https://www.websequencediagrams.com)
