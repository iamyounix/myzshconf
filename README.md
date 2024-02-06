# myzshelconf

![OS](https://img.shields.io/badge/OS-Linux/Mac-white)
![Check](https://img.shields.io/badge/Status-Pass-brightgreen)
![Information](https://img.shields.io/badge/Information-Terminal-yellow)

Table of content:

- [Introduction](#introduction)
- [Installation](#installation)
  - [Mac](#mac)
  - [Linux](#linux)
  - [Oh My ZSH](#oh-my-zsh)
  - [Plugins Installation](#plugins-installation)
- [Configuration](#configuration)
- [Acknowledgement](#acknowledgement)

## Introduction

The `Z shell` (also known as `zsh`) is a Unix shell that is built on top of bash (the default shell for macOS) with additional features. It's recommended to use zsh over bash. It's also highly recommended to install a framework with `zsh` as it makes dealing with configuration, plugins and themes a lot nicer. 

## Installation

Here, we will start `z shell` installation.

### Mac

 - Most mac already have this feature, zsh will be default after [Oh My Zsh](https://ohmyz.sh/) installation.

### Linux

 - To check, use this command `echo $0`. If the output is `bash`, proceed installation with command below:

   **Ubuntu**

   ```bash
   sudo apt install zsh
   ```

   **Fedora**

   ```bash
   sudo dnf install zsh
   ```

   **Arch**

   ```bash
   sudo pacman -S zsh
   ```

2. Check zsh version

   ```zsh
   zsh --version
   ```

3. This feature require modified fonts, .  NerdFonts need to be installed. Since there was too many font available online, you may download here:
	 - [Source 1](https://www.nerdfonts.com/font-downloads)
	 - [Source 2](https://www.nerdfonts.com/)

4. After install, terminal need to be restart.

### Oh My ZSH

1. To begin installing `omz`, copy and paste the code below to any terminal. Please follow the required (pre & post-process) step and make sure your terminal uses `zsh` by default.

   ```zsh
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

### Plugins Installation

1. Install zsh-autosuggestions

   ```zsh
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   ```
   
2. Install zsh-syntax-highlighting

   ```zsh
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   ```

3. Install zsh-autocomplete

   ```zsh
   git clone https://github.com/marlonrichert/zsh-autocomplete.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autocomplete
   ```
   
## Configuration

1. Open terminal, open `zshrc` configuration file and start configure basic needs.

   ```zsh
   sudo nano ~/.zshrc
   ```

2. Find `ZHS_THEME="robbyrussel"` to `ZHS_THEME="your_theme"`. Checkout this [wiki](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) and choose. 

3. Find `plugins=(git)` section on the same documents. Add this comment after `git`, 
	 - i.e. `git zsh-autosuggestions zsh-syntax-highlighting zsh-autocomplete`

4. Change chosen nerdfonts to your terminal.

## Acknowledgement

[**arch aur**](https://aur.archlinux.org/packages/anycable-go) | [**oh my zsh**](https://ohmyz.sh)
