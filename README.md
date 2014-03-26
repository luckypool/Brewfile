Brewfile
========

Bacis Brewfile

## Prepare

### Create Apple ID

https://developer.apple.com/register/index.action

### Install Xcode (Cmmand Line Tools)

Install from App Store

- https://itunes.apple.com/us/app/xcode/id497799835?ls=1&mt=12

Install Command Line Tools

- by CUI (open Terminal.app and do following command)

```
$ xcode-select --install
```

- or download manually

```
open Xcode.app > Open Developer tool > More Developer tool
```

## Setup Homebrew

```
$ git clone https://github.com/luckypool/Brewfile.git
$ cd Brewfile
$ rake brew:setup
```

Then, install homebrew

## Install 

```
$ rake brew:bundle
# or
$ brew bundle
```

