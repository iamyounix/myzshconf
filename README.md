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

* Recommend Download: [Fira Nerd Fonts](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.2.2/FiraCode.zip), extract downloaded fonts and install using any **Appearence / Font Management** `1`, **Global Theme / FontManagement** `2` to **Group / System Fonts** `3` by select **Install from File** `4`.

  * Font Management

![Screenshot_20221202_231257](https://user-images.githubusercontent.com/72515939/205325060-933e84ea-30bc-411e-b7c7-dc6d365ba5cd.png)

### Install zsh-autosuggestions

```zsh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
> **Note**: This will automatically install **auto-suggestions** plugins inside **Oh My ZSH** custom directory. 

### Install highlight syntax

```zsh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
> **Note**: This will automatically install **syntax-highlighting** plugins inside **Oh My ZSH** custom directory.

### Configure powerlevel10k

```zsh
p10k configure 
```

## Beautify

### Setting Terminal

* Use downloaded font on terminal settings

![AAA](https://user-images.githubusercontent.com/72515939/204857692-e74ba764-4200-4f47-b7e6-29099bb60fe7.png)

> **Note**: For better result on macOS, install iTerm2 and set font using downloaded font.

```zsh
brew install iterm2
```

### Editing zsh config
```zsh
sudo nano ~/.zshrc
```

  * Set this section

```nano
# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="powerlevel10k/powerlevel10k"
```

  * and add `zsh-autosuggestions` + `zsh-syntax-highlighting`

```nano
# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

## Results

* Linux

![Screenshot_20221202_230721](https://user-images.githubusercontent.com/72515939/205324364-a0687f4f-7ba1-4395-a3a7-ec6ffe46ffc0.png)

## Extra

### ILoveCandy

Adding pacman like progress bar on terminal (Arch Linux)

Enter this command:
```zsh
sudo nano /etc/pacman.conf 
```

and add ILoveCandy at `#Misc option` section

```nano
# Misc options
#UseSyslog
Color
ParallelDownloads = 5
# We cannot check disk space from within a chroot environment
#CheckSpace
#VerbosePkgLists
ILoveCandy
```
