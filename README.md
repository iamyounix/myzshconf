# Z Shell Configuration

![OS](https://img.shields.io/badge/OS-Linux/Mac-white)
![Check](https://img.shields.io/badge/Status-Pass-brightgreen)
![Information](https://img.shields.io/badge/Information-Terminal-yellow)

Table of content

- [Introduction](#introduction)
- [Z Shell](#z-shell)
  - [Plugins Installation](#plugin-installation)
  - [Configuration](#configuration)
- [Acknowledgement](#acknowledgement)

## Introduction

The Z shell (also known as zsh) is a Unix shell that is built on top of bash (the default shell for macOS) with additional features. It's recommended to use zsh over bash. It's also highly recommended to install a framework with zsh as it makes dealing with configuration, plugins and themes a lot nicer. We've also included an env.sh file where we store our aliases, exports, path changes etc. We put this in a separate file to not pollute our main configuration file too much. This file is found in the bottom of this page.

## Z Shell

Here, we will use Arch Linux as an example for Z Shell installation.

- **Mac**
  - Z Shell (zsh) became the default in macOS Catalina. Zsh is only the default shell on newly created user accounts, so any existing accounts you have on an upgraded Mac will still use Bash by default unless you change it.
- **Arch**

  - Install required file. To check, use this command `echo $0`. If the output is `bash`, proceed installation with command below:

    - **Ubuntu**

    ```bash
    sudo apt install zsh
    ```

    - **Fedora**

    ```bash
    sudo dnf install zsh
    ```

    - **Arch**

    ```bash
    sudo pacman -S zsh
    ```

  - Check zsh version by `zsh --version`
  - Install `Nerfonts`. Choose any [Nerd Fonts](https://www.nerdfonts.com/font-downloads), extract downloaded fonts and install.
  - Use downloaded font on terminal settings, choose mono type font. ie: `FiraCode Nerd Font Mono` to your Terminal.
  - To begin installing **oh my zsh**, copy and paste the code below to any terminal. Please follow the required (pre & post-process) step and make sure your terminal uses `zsh` by default.

    ```zsh
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```

  - If you are having trouble setting 'zsh' as your default shell, you have two options:
    - Refer [**jakewiesler**/zsh-as-default-shell](https://www.jakewiesler.com/blog/zsh-as-default-shell) to complete the step.
    - Create new terminal profile and set terminal to use `zsh` shell manually by change `usr/bin/bash` to `usr/bin/zsh` or `bin/bash` to `bin/zsh`.

### Plugins Installation

- zsh-autosuggestions

  ```zsh
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  ```

  > **Note**: This will automatically install `auto-suggestions` plugins inside **Oh My ZSH** custom directory.

- zsh-highlight-syntax

  ```zsh
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  ```

  > **Note**: This will automatically install `syntax-highlighting` plugins inside **Oh My ZSH** custom directory.

- zsh-autocomplete

  ```zsh
  git clone https://github.com/marlonrichert/zsh-autocomplete.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autocomplete
  ```

  > **Note**: This will automatically install `zsh-autocomplete` plugins inside **Oh My ZSH** custom directory.

### Configuration

- Open terminal, open `zshrc` configuration file and start configure basic needs.

  ```zsh
  sudo nano ~/.zshrc
  ```

  - Set this section

  ```zsh
  # Set name of the theme to load --- if set to "random", it will
  # load a random theme each time oh-my-zsh is loaded, in which case,
  # to know which specific one was loaded, run: echo $RANDOM_THEME
  # See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
  ZSH_THEME="your theme"
  ```

  > **Note**: Please refer this thi [link](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) to choose your favourite theme.

  - Add `zsh-autosuggestions` , `zsh-syntax-highlighting` and `zsh-autocomplete`.

  ```zsh
  # Which plugins would you like to load?
  # Standard plugins can be found in $ZSH/plugins/
  # Custom plugins may be added to $ZSH_CUSTOM/plugins/
  # Example format: plugins=(rails git textmate ruby lighthouse)
  # Add wisely, as too many plugins slow down shell startup.
  plugins=(git zsh-autosuggestions zsh-autocomplete zsh-syntax-highlighting)
  ```

## Acknowledgement

[**arch aur**](https://aur.archlinux.org/packages/anycable-go) | [**oh my zsh**](https://ohmyz.sh)
