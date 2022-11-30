# My ZSH setting
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
Recommend Download: [Fira Nerd Fonts](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.2.2/FiraCode.zip), extract downloaded fonts and install using any Font Manager `1` to System `2`.

![Font](https://user-images.githubusercontent.com/72515939/204844204-708e1795-91cc-4cf8-a296-70e07ae4a3d7.png)

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

### Editing zsh config
```zsh
sudo nano ~/.zshrc
```
> **Note**: Depending on user need, either use vim or vifs for macOS.

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
![ZSH](https://user-images.githubusercontent.com/72515939/204844248-9e3a6650-7f6b-4db8-9312-93cab58d6776.png)
