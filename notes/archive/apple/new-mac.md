# macOS

Wants:

* Apple Health app for iPad
  * I want to be able to view my Apple Health information on my iPad

## New Mac Setup

[https://brew.sh](https://brew.sh)

```bash
brew install \
  ack \
  fpp \
  fzf \
  git \
  hub \
  macvim \
  watch \
  watchman \
  yarn
```

dotfiles [https://github.com/aizatto/dotfiles](https://github.com/aizatto/dotfiles)

```bash
mkdir src
cd src
git clone https://github.com/aizatto/dotfiles.git
cd dotfiles
./install.sh
```

[https://github.com/Homebrew/homebrew-cask/tree/master/Casks](https://github.com/Homebrew/homebrew-cask/tree/master/Casks)

```bash
brew cask install \
    docker \
    iterm2 \
    kitematic \
    little-snitch \
    navicat-premium \
    postico \
    postman \
    sequel-pro \
    visual-studio-code \
    vlc
```

[Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli):

```bash
brew tap heroku/brew && brew install heroku
```

* [Generate SSH Key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

```bash
curl https://sdk.cloud.google.com | bash
```



### Apps

* [1Password](https://1password.com)
* * [https://agilebits.com/onepassword/extensions](https://agilebits.com/onepassword/extensions)
* [Day One](https://itunes.apple.com/us/app/day-one/id1055511498?mt=12)
* [Divvy](https://itunes.apple.com/us/app/divvy-window-manager/id413857545?mt=12)
* [Docker](https://store.docker.com/editions/community/docker-ce-desktop-mac)
* [Dropbox](https://www.dropbox.com/downloading?src=index)
* [iTerm](https://www.iterm2.com)
* [Google Chrome](https://www.google.com/chrome/)
* [Little Snitch](https://www.obdev.at/products/littlesnitch/index.html)
* [macvim](https://github.com/macvim-dev/macvim/releases)
* [nvALT](http://brettterpstra.com/projects/nvalt/)
* [Spotify](https://www.spotify.com/my-en/download/)
* [Sonos](https://www.sonos.com/en/controller-app)
* [Visual Studio Code](https://code.visualstudio.com/)
* [VLC](http://www.videolan.org)
* [Xcode](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)

Controlling Sound \(to HDMI/DisplayPort/USB-C\)

* [https://www.reddit.com/r/MacOS/comments/9nipy4/samsung\_c43j89\_monitor\_on\_macbook\_pro\_2018\_no/](https://www.reddit.com/r/MacOS/comments/9nipy4/samsung_c43j89_monitor_on_macbook_pro_2018_no/)
* [https://github.com/the0neyouseek/MonitorControl/releases](https://github.com/the0neyouseek/MonitorControl/releases)

### Programming

* Node.js: [nvm](https://github.com/creationix/nvm)
* Ruby: [rvm](https://rvm.io/)

### System Preferences

* Displays &gt; Scaled &gt; More Space
* Keyboard &gt; Text &gt; Disable Correct spelling automatically
* Keyboard &gt; Keyboard &gt; Key Repeat &gt; Fast
* Keyboard &gt; Keyboard &gt; Delay Until Repeat &gt; Right of Center
* Keyboard &gt; Keyboard &gt; Modifier Keys &gt; Change Caps Lock to Control
* Trackpad &gt; Max
* Bluetooth &gt; Show Bluetooth in menu bar
* Security & Privacy &gt; General &gt; Show a message when the screen is locked: If found, please contact example@example.com
* Sound &gt; Show volume in menu bar
* Sharing &gt; Name

### Contacts

* Sort By &gt; First Name

### Touchbar

* Brightness Slider
* Mute
* Volume Slider

![](../../../.gitbook/assets/touch-bar-shot-2019-03-27-at-10.49.05-pm.png)

## iTerm

* [Shell Integration](https://iterm2.com/shell_integration.html)

Alternative Terminals

* [alacritty](https://github.com/jwilm/alacritty)
* [Hyper](https://hyper.is/)
* [kitty](https://sw.kovidgoyal.net/kitty/)

