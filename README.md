# Simple ZSH settings
My Simple ZSH setting for my terminal

## Recipe

### Install [zsh](https://aur.archlinux.org/):
```zsh
sudo pacman -Sy zsh
```

### Install [Oh My Zsh](https://ohmyz.sh/)
```zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k) in [Oh My Zsh](https://ohmyz.sh/) custom directory
```zsh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

### Install [Nerfonts](https://www.nerdfonts.com/font-downloads)
Recommend Download: [Fira Nerd Fonts](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.2.2/FiraCode.zip), extract downloaded fonts and install using any Font Management `1`, `2` to System `3`.

**Linux:** Font Management

![Screenshot_20221201_003840](https://user-images.githubusercontent.com/72515939/204856525-45f215d7-24cc-47fe-80b4-805f57337e54.png)

**macOS:** Font Book

![Font Book](https://user-images.githubusercontent.com/72515939/204859719-350922f2-5894-4e58-9760-10f7babaa0b7.png)

### Install zsh-autosuggestions
```zsh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Install highlight syntax
```zsh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### Configure powerlevel10k
```zsh
p10k configure 
```

## Beautify

### Setting Terminal
Use downloaded font on terminal settings

* Linux

![AAA](https://user-images.githubusercontent.com/72515939/204857692-e74ba764-4200-4f47-b7e6-29099bb60fe7.png)

* macOS

> **Note**: For better result on macOS, install iTerm2 and set font using downloaded font.
```zsh
brew install iterm2
```

![Settings](https://user-images.githubusercontent.com/72515939/204859324-50ffdc7b-f47b-4e9e-b8de-744fff0fcfa6.png)

### Editing zsh config
```zsh
sudo nano ~/.zshrc
```

Set this section

```nano
# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="powerlevel10k/powerlevel10k"
```

and add `zsh-autosuggestions` + `zsh-syntax-highlighting`

```nano
# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

* Linux

![Screenshot_20221201_003942](https://user-images.githubusercontent.com/72515939/204856781-c7e4af0a-187f-43cd-a30b-316b48426369.png)

* macOS

![iTerm2](https://user-images.githubusercontent.com/72515939/204859048-7fdfb227-866a-47d7-8cf2-1efaec92b15b.png)
