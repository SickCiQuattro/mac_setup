## My Mac Setup

This repo contains info on all the apps / tools / settings I use on my Mac.

## What Macbook do I have?

I am using a 2024 13" Macbook Air

The specs:
* 2024
* Apple M3 8/10 core
* 16GB RAM
* 500GB SSD

## OS Settings

These are my preferred settings for `Desktop`, `Finder` and the `Dock`.

### Desktop

Wallpaper from [Astronomy Picture of the Day Archive](https://apod.nasa.gov/apod/archivepix.html)

* System Preferences
  * Desktop & Dock
    * Desktop & Stage Manager
      * Show Items
        * On Desktop -> check
        * In Stage Manager -> uncheck
      * Click wallpaper to reveal desktop -> Always
      * Stage Manager -> uncheck
      * Widgets
        * On Desktop -> check
        * In Stage Manager -> uncheck

### Finder

* Finder -> Preferences
  * General -> New Finder windows show -> Home Folder
      * I prefer to see my home folder in each new finder window instead of recent documents
  * Advanced -> Show all filename extensions -> Yes
  * Advanced -> When performing a search -> Search the current folder
* View
  * Show Status Bar
  * Show Path Bar
  * Show Tab Bar

### Dock

* System Preferences
  * Desktop & Dock
    * Size -> Mid
    * Position on screen -> Bottom
    * Automatically hide and show the Dock -> Yes
    * Animate opening applications -> Yes
    * Show suggested and recent apps in the Dock -> Yes

keep smooth animation time, but remove delay:
```sh
defaults write com.apple.dock autohide-delay -float 0; killall Dock
```

instantly reveal:
```sh
defaults write com.apple.dock autohide-time-modifier -int 0; killall Dock
```

restore default behavior:
```sh
defaults delete com.apple.dock autohide-delay; killall Dock`
```

## Quick Launching

The built in spotlight search is a bit slow for me and usually has web search results as the default instead of apps or folders on my machine.

I switched to [RayCast](https://www.raycast.com/). I'm really liking it so far.

```sh
brew install raycast
```

## Homebrew

### Homebrew

[Homebrew](https://brew.sh/) allows us to install tools and apps from the command line.

To install it, open up the built in `Terminal` app and run this command:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This will also install the xcode build tools which is needed by many other developer tools.

After Homebrew is done installing, we will use it (via RayCast) to install everything else we need.


### RayCast Homebrew Plugin

Install the [RayCast Homebrew Plugin](https://www.raycast.com/nhojb/brew) so we can easily install formulae and casks directly from RayCast.

## Window Management

I know this feature is built in to a lot of other operating systems, but it is not built in to a Mac, so we need an app for it.

RayCast has this feature built in, but I am still using a separate app for this.

I use [rectangle](https://rectangleapp.com/) to move and resize windows using keyboard shortcuts.

I highly recommend installing this and memorizing the keyboard shortcuts. Fluid and seamless window management is key to being productive while coding.

Search for `rectangle` in RayCast `brew search` or:

```
brew install rectangle
```

## Menu Bar Utilities

### Hidden Bar

If you have several apps running that have menu bar icons, [Hidden Bar](https://github.com/dwarvesf/hidden) will let you choose which ones should be hidden after a timeout. This cleans things up if you have a ton of background apps running.

Search for `hiddenbar` in RayCast `brew search` or:

```sh
brew install hiddenbar
```

### System Stats Widgets

I use [stats](https://github.com/exelban/stats) to see my network traffic, CPU temp / usage and RAM usage at a glance.

In each widget, a key setting to look for is under "widget settings", choose "merge widgets into one".

Search for `stats` in RayCast `brew search` or:

```sh
brew install stats
```

### Take text from screen
I use [TRex](https://github.com/amebalabs/TRex) to capture any text right into my Clipboard

I use the shortcut CMD+Shift+2 to take the text quickly.

```sh
brew install trex
```

### Clean Copy Text
I use [Clean Copy](https://apps.apple.com/it/app/pure-paste/id1611378436?mt=12) to clean text in clipboard.
Free in App Store.

### Firewall
I use [LuLu](https://github.com/objective-see/LuLu?tab=readme-ov-file).

```sh
brew install lulu
```

## Break Timer

I use an app called [Time Out](https://www.dejal.com/timeout/).

I have it setup to show:
* 10 second micro break every 15 minutes
* 5 minute long break every 60 minutes

There is also a cross platform break timer call [Stretchly](https://hovancik.net/stretchly/). I have not used it but a lot of people have recommended it.

## Web Browser

### Arc

I'm learning [Arc](https://arc.net) for fastest web searching.



## Other Apps I Use Daily

* 
* [keka](https://www.keka.io/en/) - Can extract 7z / rar and other types of archives
* Pure Past
* Latest
* AppCleaner
* BoringNotch
* Trex
* Ice
* BatFi
* LuLu
* IINA
* [visual-studio-code](https://code.visualstudio.com/) - Code Editor

You can install them in one go by placing them all into a text file and then running brew install:

```
keka
purepast
latest
appcleaner

trex
ice

lulu
iina
```

```sh
xargs brew install < apps.txt
```

### Docker

There are multiple results when you search `docker` within `brew`. To install Docker desktop:

```sh
brew install --cask docker
```

## Terminal

I prefer [iTerm2](https://iterm2.com/) because:
* Lots of customization options
* Clickable links
* Native OS notifications

There are a lot of options for a terminal replacement, but I've been using iTerm2 for years and it works great for my needs.

Checkout their documentation for more info on what iTerm2 can do: [https://iterm2.com/documentation.html](https://iterm2.com/documentation.html)


```
brew install iterm2
```

Once installed, launch it and customize the settings / preferences to your liking. These are my preferred settings:

* Appearance
  * Theme
    * Minimal
* Profiles
  * Default
      * General -> Working Directory -> Reuse previous session's directory
      * Colors -> PurpleRain.itermcolors
      * Text -> Font -> [Hack Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/Hack.zip)
          * I use this font in VS Code as well
      * Text -> Font Size -> 13
      * Keys -> Key Mappings -> Presets -> Natural Text Editing
          * This allows me to use the [keyboard shortcuts](https://gist.github.com/w3cj/022081eda22081b82c52) I know and love inside of iTerm2

### Shell

Mac now comes with `zsh` as the default [shell](https://en.wikipedia.org/wiki/Comparison_of_command_shells). I've switched to using this with [Oh My Zsh](https://ohmyz.sh/).

### Custom Theme

I use [Starship](https://starship.rs) for custom theme

```
brew install starship
```

### Plugins
cmatrix
eza
neofetch
toilet
amazon-q

### Sudo with TouchID

```sh
sudo nano /etc/pam.d/sudo
```
Insert in the first line:

```
auth sufficient pam_tid.so
```

### Github SSH Setup

* Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to setup an ssh key for github
* Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) to add the ssh key to your github account

### Other command line tools I use

* [ffmpeg](https://en.wikipedia.org/wiki/FFmpeg) - edit videos from the command line
* [imagemagick](https://en.wikipedia.org/wiki/ImageMagick) - edit images from the command line

```sh
brew install ffmpeg
brew install imagemagick
```

### Node.js

I use nvm to manage the installed versions of Node.js on my machine. This allows me to easily switch between Node.js versions depending on the project I'm working in.

See installation instructions [here](https://github.com/nvm-sh/nvm#installing-and-updating).

OR run this command (make sure v0.39.7 is still the latest)

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Now that nvm is installed, you can install a specific version of node.js and use it:

```sh
nvm install 20
nvm use 20
node --version
```

### Global Modules

There are a few global node modules I use a lot:

* lite-server
  * Auto refreshing static file server. Great for working on static apps with no build tools.
* http-server
  * Simple static file server.
* license
  * Auto generate open source license files
* gitignore
  * Auto generate `.gitignore` files base on the current project type

```
npm install -g lite-server http-server license gitignore
```

### VS Code

VS Code is my preferred code editor.

### Music

I use Spotify with [Spicetify](https://spicetify.app) and [Spot-X](https://github.com/SpotX-Official/SpotX-Bash) to custom every aspect.

Easy way to [install al](https://github.com/yodaluca23/SpotX-Spicetify-Universal-Installer)

### Telegram
[Telegram Theme](https://t.me/addtheme/YWtZ0OzZyUvWNelJ)
or Strawberry.tdesktop-theme