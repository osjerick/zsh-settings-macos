# macOS powerful (visual) terminal: iTerm + Oh My Zsh + Powerline10k

![Example Shell](example.png)

## Requirements

This is a list of tools required to set up a terminal like the one shown in the picture above. Follow their installation Instructions, which are pretty well written and contain all the up-to-date required information.

1. [iTerm2](https://iterm2.com/index.html) (a much better terminal).
2. [Homebrew](https://brew.sh/) (a community-driven package manager).
3. [Oh My Zsh](https://ohmyz.sh/) (a framework for managing Zsh configurations).

   It requires Zsh as your default shell (if it's not already there; `echo $SHELL` ): https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH.

4. [Powerlevel10k](https://github.com/romkatv/powerlevel10k) (a powerful theme for Zsh).

## Oh My Zsh Plugins

To make Zsh more powerful you need plugins.

You can inspect plugins by using the `omz` command (installed with Oh My Zsh).
```shell
omz plugin list # available plugins
omz plugin info <plugin> # info about a plugin
omz plugin enable <plugin> # enable plugin
omz plugin --help # more plugin info
```

### Recommended Custom Plugins
These require Git for installation.
- [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
- [zsh-completions](https://github.com/zsh-users/zsh-completions)

## Color Customization
- [Oh My Zsh built-in themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes).
- [Powerlevel10k](https://github.com/romkatv/powerlevel10k).
  
  To ensure you have the best experience, install some custom fonts: https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k.

## iTerm2 Settings
Some useful settings.

### Color Scheme
- `Settings -> Profiles -> Colors -> Color Presets` and select a color scheme.
- You can import new presets. Presets repository: https://iterm2colorschemes.com/.
- The terminal in the image above uses `FirefoxDev` with some tweaks in Powerlevel10k settings (see example settings).

### Natural Text Editing

- `Settings -> Profiles -> Keys -> Key Mappings -> Presets` and select **Natural Text Editing**.

## Example Settings
- Oh My Zsh: [zshrc_example.zsh](zshrc_example.zsh). Several plugins are enabled, and OMZ is setup to be updated automatically.
- Powerlevel10k: [p10k_example.zsh](p10k_example.zsh). Several changes are applied to remove some icons, change the order of some elements, and make the theme more adapted to the `FirefoxDev` color scheme for iTerm2.
