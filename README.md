Brewfile
========

Bacis Brewfile

## Prepare

### Create Apple ID

https://developer.apple.com/register/index.action

### Install Xcode (Command Line Tools)

Install from App Store

- https://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12

Install Command Line Tools

- by CUI (open Terminal.app and do following command)

```bash
$ xcode-select --install
```

- or download manually

```
open Xcode.app > Open Developer tool > More Developer tool
```

## Setup Homebrew

```bash
$ git clone https://github.com/luckypool/Brewfile.git
$ cd Brewfile
$ rake brew:setup
```

Then, install homebrew

## Install by Brewfile

```bash
$ rake brew:bundle

# or

$ brew bundle
```

## Package list

### by homebrew

- git
- hub
- jq
- nkf
- openssl
- terminal-notifier
- tig
- tmux
- tree
- zsh
- zsh-completions

### by [homebrew-cask](https://github.com/phinze/homebrew-cask)

- android-studio
- appcleaner
- bettertouchtool
- google-chrome
- iterm2
- java
- keyremap4macbook
- kobito
- limechat
- sublime-text
- virtualbox
- vagrant
- xtrafinder

