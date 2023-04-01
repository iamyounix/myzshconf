# Z Shell Configuration

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

The `Z shell` (also known as `zsh`) is a Unix shell that is built on top of bash (the default shell for macOS) with additional features. It's recommended to use zsh over bash. It's also highly recommended to install a framework with `zsh` as it makes dealing with configuration, plugins and themes a lot nicer. We've also included an env.sh file where we store our aliases, exports, path changes etc. We put this in a separate file to not pollute our main configuration file too much. This file is found in the bottom of this page.

## Installation

Here, we will start `z shell` installation.

### Mac

`Z Shell` became the default in macOS Catalina. Zsh is only the default shell on newly created user accounts, so any existing accounts you have on an upgraded Mac will still use `bash` by default unless you change it.

### Linux

1. Install required file. To check, use this command `echo $0`. If the output is `bash`, proceed installation with command below:

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

   ![version](https://user-images.githubusercontent.com/72515939/229268347-1e35b52a-410e-4ab7-a785-dad566e56b04.png)

3. Install `Nerfonts`. Choose any [Nerd Fonts](https://www.nerdfonts.com/font-downloads)

4. Extract downloaded fonts and install or visit [here](https://github.com/ryanoasis/nerd-fonts#font-patcher) for more installation method.

5. Use downloaded font on terminal settings, set mono type font. ie: `FiraCode Nerd Font Mono` to your Terminal.

### Oh My ZSH

1. To begin installing `omz`, copy and paste the code below to any terminal. Please follow the required (pre & post-process) step and make sure your terminal uses `zsh` by default.

   ```zsh
   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

2. If you are having trouble setting `zsh` as your default shell, you have two options:

3. Refer [jakewiesler*/zsh-as-default-shell](https://www.jakewiesler.com/blog/zsh-as-default-shell) to complete the step.

4. Create new terminal profile and set terminal to use `zsh` shell manually by change `usr/bin/bash` to `usr/bin/zsh` or `bin/bash` to `bin/zsh`.

### Plugins Installation

1. Install zsh-autosuggestions

   ```zsh
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   ```
2. Install zsh-highlight-syntax

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

2. Set this section

   ![name](https://user-images.githubusercontent.com/72515939/229268420-d30baf0c-e8eb-4a93-a8ed-9a486f8cd46a.png)

   > **Note**: Please refer this thi [link](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) to choose your favourite theme.

3. Add `zsh-autosuggestions` , `zsh-syntax-highlighting` and `zsh-autocomplete`.

   ![plugin](https://user-images.githubusercontent.com/72515939/229268427-fe94e8b6-1041-4f9d-97f0-c7c1f2f35f03.png)

   ![2023-04-01 14-50-33](https://user-images.githubusercontent.com/72515939/229271070-751bf715-a80f-426c-b1ec-bd49519f2e3b.gif) 

## Acknowledgement

[**arch aur**](https://aur.archlinux.org/packages/anycable-go) | [**oh my zsh**](https://ohmyz.sh)
