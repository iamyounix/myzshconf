# Z Shell Configuration

![OS](https://img.shields.io/badge/OS-Arch-white)
![Check](https://img.shields.io/badge/Status-Pass-brightgreen)
![Information](https://img.shields.io/badge/Information-Terminal-yellow)

Table of content

- [Introduction](#introduction)
  - [Z Shell](#z-shell)
  - [Powerlevel10k](#powerlevel10k)
    - [Configure Z Shell](#configure-z-shell)
    - [Install System Info](#install-system-info)
  - [Results](#results)
- [Acknowledgement](#acknowledgement)

## Introduction

The Z shell (also known as zsh) is a Unix shell that is built on top of bash (the default shell for macOS) with additional features. It's recommended to use zsh over bash. It's also highly recommended to install a framework with zsh as it makes dealing with configuration, plugins and themes a lot nicer. We've also included an env.sh file where we store our aliases, exports, path changes etc. We put this in a separate file to not pollute our main configuration file too much. This file is found in the bottom of this page.

## Z Shell

Here, we will use Arch Linux as an example for Z Shell installation.

- Arch:

    ```bash
    sudo pacman -S zsh
    ```

    1. Install `Nerfonts`. Recommend to download: [Fira Code Nerd Fonts](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.2.2/FiraCode.zip), extract downloaded fonts and install.
    2. Use downloaded font on terminal settings, choose mono type font. ie: `FiraCode Nerd Font Mono` to your Terminal.
    3. Install `Oh My Zsh`. Open terminal, copy and paste code below to start installation

        ```zsh
        sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
        ```

## Powerlevel10k

Powerlevel10k is a theme for `Z` shell. It emphasizes speed, flexibility and out-of-the-box experience.

- Install Powerlevel10k

    1. Clone zsh to custom directory

        ```zsh
        git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
        ```

    2. Install zsh-autosuggestions

        ```zsh
        git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
        ```

        > **Note**: This will automatically install `auto-suggestions` plugins inside **Oh My ZSH** custom directory. Refer [Editing zsh config](https://github.com/theofficialcopypaste/SimpleZSHSettings/blob/main/README.md#editing-zsh-config) to add auto-suggestions plugin

    3. Install highlight syntax

        ```zsh
        git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
        ```

        > **Note**: This will automatically install `syntax-highlighting` plugins inside **Oh My ZSH** custom directory. Refer [Editing zsh config](https://github.com/theofficialcopypaste/SimpleZSHSettings/blob/main/README.md#editing-zsh-config) to add syntax-hightlighting plugin

- Configure Powerlevel10k

  - Required if zsh configuration does not automatically start

    ```zsh
    p10k configure 
    ```

    > **Note**: Refer [Editing zsh config](https://github.com/theofficialcopypaste/SimpleZSHSettings/blob/main/README.md#editing-zsh-config) to configure theme.

### Configure Z Shell

We need to configure `zsh` to the required state. The configuration is shown below:

- Oh My ZSH configuration settings

    ```zsh
    sudo nano ~/.zshrc
    ```

    1. Set this section

        ```nano
        # Set name of the theme to load --- if set to "random", it will
        # load a random theme each time oh-my-zsh is loaded, in which case,
        # to know which specific one was loaded, run: echo $RANDOM_THEME
        # See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
        ZSH_THEME="powerlevel10k/powerlevel10k"
        ```

    2. Add `zsh-autosuggestions` + `zsh-syntax-highlighting`

        ```nano
        # Which plugins would you like to load?
        # Standard plugins can be found in $ZSH/plugins/
        # Custom plugins may be added to $ZSH_CUSTOM/plugins/
        # Example format: plugins=(rails git textmate ruby lighthouse)
        # Add wisely, as too many plugins slow down shell startup.
        plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
        ```

    3. Additional for Arch. Install `ILoveCandy`, a `pacman` ⍩⃝ like `progress bar` on terminal (Arch Linux)

        1. Enter this command:

            ```zsh
            sudo nano /etc/pacman.conf 
            ```

        2. Add `ILoveCandy` below `#Misc option` section

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

### Install System Info

Now, we need to install another tool called `Neofetch`. Neofetch is a super-convenient command-line utility used to fetch system information within a few seconds. It is cross-platform, open-source, and it displays everything ranging from your system’s uptime to the Linux kernel version.

- Adding system info

    1. Install `neofetch`.

        ```zsh
        sudo pacman -Sy neofetch
        ```

    2. Prompt quiet mode to ensure `neofetch` bypass `powerlevel10k` [warning].

        ```zsh
        sudo nano ~/.p10k.zsh
        ```

    3. Find `typeset -g POWERLEVEL9K_INSTANT_PROMPT=verbose` and change this mode to `quiet`. ie: `typeset -g POWERLEVEL9K_INSTANT_PROMPT=quiet`.
    4. Save config and head to `~/.zshrc` config.

        ```zsh
        sudo nano ~./zshrc
        ```

    5. Add `neofetch` on ending.

        ```zsh
        # To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
        [[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

        neofetch
        ```

## Results

![Arch](https://user-images.githubusercontent.com/72515939/215356327-2d6c8f9f-c616-48a6-af30-37c2fb5454a3.png)

## Acknowledgement

[**arch aur**](https://aur.archlinux.org/packages/anycable-go) | [**oh my zsh**](https://ohmyz.sh) | [**romkatv**](https://github.com/romkatv)
