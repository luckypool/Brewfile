# Brewfile

https://github.com/luckypool/Brewfile

開発環境つくるの面倒

でもコマンド一発でなんとかするやつ


---

# その前に

---

## Xcode / homebrew

詳しくは [README.md](https://github.com/luckypool/Brewfile/blob/master/README.md)

--

### (1) Create Apple ID

https://developer.apple.com/register/index.action

--

### (2) Install Xcode

(and Command Line Tools)

##### [Install via AppStore](https://itunes.apple.com/jp/app/xcode/id497799835)

run Xcode.app or do `sudo xcodebuild -license`

```
$ xcode-select --install
```

--


## (3) homebrew

ターミナルで実行！

```
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

or

```
$ git clone https://github.com/luckypool/Brewfile.git
$ cd Brewfile
$ rake brew:setup
```

--

## 以上

これで Xcode / homebrew おｋ

---

## Brewfileの話

--

Brewfile の例

```
update
upgrade

install git

tap phinze/homebrew-cask || true
install brew-cask

cask install google-chrome

cleanup
```

なんとなく分かりますね

<small>https://github.com/luckypool/Brewfile/blob/master/Brewfiles/minimal</small>


--


## USAGE

```
$ brew bundle ./Brewfiles/minimal

# or

$ rake brew:bundle
```

以上！

--

### 以下補足


[brew-bundle.rb](https://github.com/Homebrew/homebrew/blob/master/Library/Contributions/cmd/brew-bundle.rb)
でやってることは、

ファイルの中身の1行毎に

```
system "brew #{command}"
```

ってやってるだけ。シンプル。

--

[Brewfiles](https://github.com/luckypool/Brewfile/tree/master/Brewfiles)

詳しくはファイルの中身で！

お気の召すままにカスタマイズするのが良いとおもう :)

--

探し方は

```
$ brew cask search hogehoge
```

もしくは [homebrew-cask/Casks](https://github.com/phinze/homebrew-cask/tree/master/Casks)


---


## あと anyenv

https://github.com/riywo/anyenv

http://qiita.com/luckypool/items/f1e756e9d3e9786ad9ea

--

#### セットアップ

```
$ rake anyenv:setup

# or 

$ git clone https://github.com/riywo/anyenv ~/.anyenv
```

--

#### PATH

<small>.zshrc / .bashrc などに</small>

```
if [ -d ${HOME}/.anyenv ] ; then
    export PATH="$HOME/.anyenv/bin:$PATH"
    eval "$(anyenv init -)"
    for D in `ls $HOME/.anyenv/envs`
    do
        export PATH="$HOME/.anyenv/envs/$D/shims:$PATH"
    done
fi
```

<small>
設定後 `exec $SHELL -l` 忘れずに
</small>

--

#### インストール


```
$ rake anyenv:install

# and do 

$ exec $SHELL -l
```

<small>
(plenv / rbenv / ndenv がはいるよ！)
</small>


--


#### ビルドとglobalへの設定


```
$ rake anyenv:build
```

<small>
(perl 5.14.4 / ruby 2.1.0 / node v0.10.26 がglobalに設定されるよ！)
</small>


--

## 以上 :)


---

# おわり

<small>
[README](https://github.com/luckypool/Brewfile/blob/master/README.md)も見てね
</small>

