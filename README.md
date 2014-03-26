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

