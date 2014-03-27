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

Please choose branch

- [master/Brewfile](https://github.com/luckypool/Brewfile/blob/master/Brewfile)
- [minimal/Brewfile](https://github.com/luckypool/Brewfile/blob/minimal/Brewfile)
- or edit Brewfile as you like.

ex.) If you like minimal Brewfile

```
$ git checkout -b minimal origin/minimal
```

## Install anyenv

```bash
$ rake anyenv:setup
```

Add to your .bashrc or .zshrc

```
export PATH="$HOME/.anyenv/bin:$PATH"
eval "$(anyenv init -)"
for D in `ls $HOME/.anyenv/envs`
do
    export PATH="$HOME/.anyenv/envs/$D/shims:$PATH"
done
```

and do `exec $SHELL -l`

## Install plenv, rbenv, ndenv

```bash
$ rake anyenv:install
```

will be installed 

- Perl 5.14.4/5.16.3
  - set 5.14.4 to global
- Ruby 2.1.0
- Node.js v0.10.25

