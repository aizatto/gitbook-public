# macOS

Wants:

* Apple Health app for iPad
  * I want to be able to view my Apple Health information on my iPad

## New Mac Setup

[https://brew.sh](https://brew.sh)

```bash
brew install \
  ack \
  fish \
  fpp \
  fzf \
  git \
  hub \
  macvim \
  mosh \
  pyenv \
  watch \
  watchman \
  yarn
  
brew install MisterTea/et/et
```

dotfiles [https://github.com/aizatto/dotfiles](https://github.com/aizatto/dotfiles)

```bash
mkdir src
cd src
git clone git@github.com:aizatto/dotfiles.git
cd dotfiles
./install.sh
```

[https://github.com/Homebrew/homebrew-cask/tree/master/Casks](https://github.com/Homebrew/homebrew-cask/tree/master/Casks)

```bash
brew cask install \
    docker \
    iterm2 \
    kitematic \
    postman \
    spotify \
    visual-studio-code \
    vlc
    
# Issues with these
brew cask install \
  little-snitch \
  navicat-premium
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
* [GeekBench](https://www.geekbench.com/download/)
* [Google Chrome](https://www.google.com/chrome/)
* [Little Snitch](https://www.obdev.at/products/littlesnitch/index.html)
* Logitech
  * [https://support.logi.com/hc/en-us/articles/360034763274-Download-Stub-MX-Master-3-Wireless-Mouse-with-Hyper-fast-Scroll-Wheel](https://support.logi.com/hc/en-us/articles/360034763274-Download-Stub-MX-Master-3-Wireless-Mouse-with-Hyper-fast-Scroll-Wheel)
  * Point and Scroll &gt; Scrolling Speed &gt; 90% to the right
  * Scroll direction: Natural
* [macvim](https://github.com/macvim-dev/macvim/releases)
* [navicat](https://navicat.com/en/download/navicat-premium)
* [nvALT](http://brettterpstra.com/projects/nvalt/)
* [Spotify](https://www.spotify.com/my-en/download/)
* [Sonos](https://www.sonos.com/en/support)
* [Visual Studio Code](https://code.visualstudio.com/)
* [VLC](http://www.videolan.org)
* [Xcode](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)
* [Eternal Terminal](https://eternalterminal.dev/download/)

Controlling Sound \(to HDMI/DisplayPort/USB-C\)

* [https://www.reddit.com/r/MacOS/comments/9nipy4/samsung\_c43j89\_monitor\_on\_macbook\_pro\_2018\_no/](https://www.reddit.com/r/MacOS/comments/9nipy4/samsung_c43j89_monitor_on_macbook_pro_2018_no/)
* [https://github.com/the0neyouseek/MonitorControl/releases](https://github.com/the0neyouseek/MonitorControl/releases)

### Programming

* Node.js: [nvm](https://github.com/creationix/nvm)
* Python: [pyenv](https://github.com/pyenv/pyenv)
* Ruby: [rvm](https://rvm.io/)

nvm:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
nvm install --lts
nvm alias default $LATEST # v12.16.2
nvm use default
```

rvm:

```text
curl -sSL https://get.rvm.io | bash -s stable
rvm list known
rvm install ruby-2.7
```

[pyenv](https://github.com/pyenv/pyenv):

```bash
pyenv install --ls
pyenv install $LATEST # 3.8.2
```

### System Preferences

In macOS Catalina \(top left to bottom right\)

* Dock &gt; Disable "show recent applications in Dock"
* Touch ID
* Security & Privacy &gt; General &gt; Show a message when the screen is locked: If found, please contact example@example.com
* Security & Privacy &gt; General &gt; Use your Apple Watch to unlock apps and your Mac
* Internet Accounts &gt; Gmail &gt; Disable Mail and Address Book
* Bluetooth &gt; Show Bluetooth in menu bar
* Sound &gt; Show volume in menu bar
* Keyboard &gt; Text &gt; Disable Correct spelling automatically
* Keyboard &gt; Keyboard &gt; Key Repeat &gt; Fast
* Keyboard &gt; Keyboard &gt; Delay Until Repeat &gt; Right of Center
* Keyboard &gt; Keyboard &gt; Modifier Keys &gt; Change Caps Lock to Control
* Trackpad &gt; Max
* Displays &gt; Scaled &gt; More Space
* Date & Time &gt; Clock &gt; Display the time with seconds
* Sharing &gt; Name
* Time Machine &gt; Options &gt; Exclude system files and applications
  * Add: /Applications, /Library /System, ~/Library

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

