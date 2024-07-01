# UTF8 Bash terminal on Windows

![v1.0.0](https://img.shields.io/badge/version-1.0.0-white.svg?style=flat-squarex&color=lightgray)
[![License](https://img.shields.io/github/license/JosePamplona/UTF8-bash-terminal-on-Windows)](https://github.com/JosePamplona/UTF8-bash-terminal-on-Windows/blob/main/LICENSE.md)
[![Last Updated](https://img.shields.io/github/last-commit/JosePamplona/UTF8-bash-terminal-on-Windows.svg)](https://github.com/JosePamplona/UTF8-bash-terminal-on-Windows/commits/main)

Instructions to set the [Git BASH](https://gitforwindows.org/) terminal with support for UTF-8 Unicode characters for Windows.

As terminal customization bonus, includes installation instructions for [Z Shell](https://www.zsh.org/) and [Oh My ZSH!](https://ohmyz.sh/).

## Steps

1. Install [Git for Windows](https://gitforwindows.org/).

1. Create or modify `C:\Users\<YOUR_USER_NAME>\.bashrc` with the following content:

    ```bash
    /c/Windows/System32/chcp.com 65001 > /dev/null 2>&1
    ```

## Bonus

1. Download [Z Shell](https://packages.msys2.org/package/zsh).

1. Extract the content of the `*.tar.gz` downloaded file in `C:\Program Files\Git` directory.

1. Append at the end of `C:\Users\<YOUR_USER_NAME>\.bashrc` file the following content:

    ```bash
    if [ -t 1 ]; then
      exec zsh
    fi
    ```

1. Install [Oh My ZSH!](https://ohmyz.sh/#install):

    ```bash
    sh -c "$(curl -fsSL <https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh>)"
    ```

1. Install [Menslo PowerLine10k patched fonts](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#meslo-nerd-font-patched-for-powerlevel10k):
    - [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
    - [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%Bold.ttf)
    - [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
    - [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

1. Install [PowerLevel10k theme](https://github.com/romkatv/powerlevel10k)

    ```bash
    git clone --depth=1 <https://github.com/romkatv/powerlevel10k.git> ~/powerlevel10k
    echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
    ```

1. Open **Git BASH** and configure the installed theme.
