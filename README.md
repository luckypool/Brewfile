Brewfile
========

Bacis Brewfile

## Prepare

### Create Apple ID

https://developer.apple.com/register/index.action

### Install Xcode (Command Line Tools)

Install from App Store

- https://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12

Agree License

- run Xcode.app and Agree
- or do `sudo xcodebuild -license`

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

## Install packages by Brewfile

```bash
$ rake brew:bundle

# or

$ brew bundle ./Brewfiles/minimal
```

### Package list

Memo : [documents/Brewfile.md](documents/Brewfile.md)

Please choose Brewfile or edit Brewfile as you like.

- [Brewfiles](Brewfiles)


## Install anyenv

### Setup

```bash
$ rake anyenv:setup
```

Then, add to your .bashrc or .zshrc

```
export PATH="$HOME/.anyenv/bin:$PATH"
eval "$(anyenv init -)"
for D in `ls $HOME/.anyenv/envs`
do
    export PATH="$HOME/.anyenv/envs/$D/shims:$PATH"
done
```

then, do `exec $SHELL -l`

### Install plenv, rbenv, and ndenv

```bash
$ rake anyenv:install
```

then, do `exec $SHELL -l`

### Build Perl, Ruby, and Node

```bash
$ rake anyenv:build
```

will be installed 

- Perl 5.14.4
- Ruby 2.1.0
- Node.js v0.10.25

## Rake tasks

```
anyenv:setup         -- setup anyenv
anyenv:install       -- install plenv, rbenv, ndenv
anyenv:build         -- build perl, ruby, node.js
brew:setup           -- setup homebrew
brew:bundle          -- bundle (minimal packages)
brew:bundle_all      -- bundle (recommended packages)
brew:bundle_android  -- bundle (only android development packages)
brew:upgrade         -- upgrade task (update, upgrade, and cleanup)```
```
