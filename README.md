# Custom ZSH Experience on macOS

## Install Homebrew
### Requirements
```bash
xcode-select --install
```

### [Homebrew](https://brew.sh/)
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```


## Install [iTerm2](https://www.iterm2.com/downloads.html)
>iTerm2 is a replacement for Terminal and the successor to iTerm. It works on Macs with macOS 10.12 or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.

Unpack the `.zip` file and move the app to `/Applications` folder.

## Install ZSH
By default macOS comes with ZSH located in `/bin/zsh`.

```bash
brew install zsh
```

## Install [Oh My ZSH](https://github.com/ohmyzsh/ohmyzsh)
>Oh My Zsh is an open source, community-driven framework for managing your zsh configuration.

Via `curl`:
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Via `wget`:
```bash
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Install Custom Plugins
Oh My ZSH comes with [lots of plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins) that could be activated from the `~/.zshrc` config file:
```bash
plugins=(
  git
  bundler
  dotenv
  osx
  rake
  rbenv
  ruby
)
```

The `~/.zshrc` config file is usually regenerated when installing Oh My Zsh, and a backup of the previous version is kept, just check your home folder with `ls -a`.

Some other plugins should be installed and added manually to the `plugin` list above to be activated (**all installation methods shown are for Oh My ZSH**):

### [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
>This package provides syntax highlighting for the shell zsh. It enables highlighting of commands whilst they are typed at a zsh prompt into an interactive terminal. This helps in reviewing commands before running them, particularly in catching syntax errors.
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
>Fish-like fast/unobtrusive autosuggestions for zsh.
>It suggests commands as you type based on history and completions.
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### [zsh-completions](https://github.com/zsh-users/zsh-completions)
>Additional completion definitions for Zsh.
>This projects aims at gathering/developing new completion scripts that are not available in Zsh yet. The scripts may be contributed to the Zsh project when stable enough.
```bash
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-completions
```

### [zsh-apple-touchbar](https://github.com/zsh-users/zsh-apple-touchbar)
>Make your touchbar more powerful.

**Requirements**:

- iTerm2 3.1 or later
- zsh
- ruby 2.3.4 or later (only if you want automatic generation)

```bash
git clone https://github.com/zsh-users/zsh-apple-touchbar $ZSH_CUSTOM/plugins/zsh-apple-touchbar
```

It is fully customizable, check the [docs](https://github.com/zsh-users/zsh-apple-touchbar#customization)!

## Customize Colors
### [Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)
>In order to enable a theme, set `ZSH_THEME` to the name of the theme in your `~/.zshrc`, before sourcing Oh My Zsh; for example: `ZSH_THEME=robbyrussell`.
>If you do not want any theme enabled, just set `ZSH_THEME` to blank: `ZSH_THEME=""`

#### [POWERLEVEL9K](https://github.com/Powerlevel9k/powerlevel9k)
>Powerlevel9k is a theme for ZSH which uses Powerline Fonts. It can be used with vanilla ZSH or ZSH frameworks such as Oh-My-Zsh, Prezto, Antigen, and many others.

##### Installation
```bash
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

Select it in your  `~/.zshrc`:
```bash
ZSH_THEME="powerlevel9k/powerlevel9k"
```

##### [Powerline Fonts](https://github.com/Powerlevel9k/powerlevel9k/wiki/Install-Instructions#step-2-install-a-powerline-font)
>In order for the theme to render properly, you need a font that has the "Powerline" glyphs. These are used at the start & end of the segments to produce the "powerline" appearance. Additionally, if your font includes any of the expanded glyph set, Powerlevel9k is capable of making use of those to produce a very nice prompt.

###### Nerd Fonts
>The Nerd-Fonts project is an effort to create fonts truly tricked out with as many glyphs as possible. After installing `nerd-fonts` and configuring your terminal emulator to use one, configure Powerlevel9k by putting the following in your `~/.zshrc` before you specify the powerlevel9k theme:
>```bash
>POWERLEVEL9K_MODE='nerdfont-complete'
>```

Example: [SF Mono Nerd Font](./SF-Mono-Regular-Nerd-Font-Complete.otf).

##### Settings
These settings generate a pretty usefull layout using Powerlevel9k:
```bash
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(user dir_writable dir vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status anaconda virtualenv)
POWERLEVEL9K_STATUS_CROSS="true"
POWERLEVEL9K_STATUS_OK="false"
POWERLEVEL9K_USER_DEFAULT_FOREGROUND="110"
POWERLEVEL9K_SHORTEN_DIR_LENGTH=2
POWERLEVEL9K_SHORTEN_DELIMITER=".."
POWERLEVEL9K_ANACONDA_FOREGROUND="071"
POWERLEVEL9K_ANACONDA_BACKGROUND="008"
POWERLEVEL9K_PYTHON_ICON=""
POWERLEVEL9K_HOME_ICON=""
POWERLEVEL9K_HOME_SUB_ICON=""
POWERLEVEL9K_FOLDER_ICON=""
POWERLEVEL9K_ETC_ICON=""
POWERLEVEL9K_VCS_GIT_ICON=""
POWERLEVEL9K_VCS_GIT_GITHUB_ICON=""
POWERLEVEL9K_VCS_GIT_GITLAB_ICON=""
POWERLEVEL9K_VCS_GIT_BITBUCKET_ICON=""
ZSH_HIGHLIGHT_STYLES[path]="none"
```

Example `~/.zshrc` [file](./zshrc_example.sh).

## iTerm2 Settings
iTerm2 is fully customizable.

### Colors
Download and install a color scheme from [iTerm2 Color Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes).

Sample color scheme: [FirefoxDev.itermcolors](./FirefoxDev.itermcolors)

### Fonts
iTerm2 allows us to set two sets of fonts for ASCII characters and for non-ASCII characters. Go to `Preferences -> Profiles -> Text -> Font` and select, for example:

- `SF Mono` Semibold `12 pt` as main **Font**. [Download Font](./SF-Mono.dmg) [Official Link](https://developer.apple.com/fonts/)
- `SFMono Nerd Font` Regular `12 pt` as **Non-ASCII Font**. [Download Font](./SF-Mono-Regular-Nerd-Font-Complete.otf)

### Keys

Go to `Preferences -> Profiles -> Keys -> Presets` and select **Natural Text Editing** for a natural typing experience.

### Profile
A profile could load all these settings from a JSON file:

Sample profile: [FirefoxDev.json](./FirefoxDev.json)

### Terminal.app Settings
The same profile, translated to Terminal.app config language:

Sample profile: [FirefoxDev.terminal](./FirefoxDev.terminal)