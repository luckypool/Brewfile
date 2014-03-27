Brewfileの説明
==============

[https://github.com/luckypool/Brewfile/blob/master/Brewfile]

## 共通の

### update/upgradeと cleanup

Brewfile の最初と最後に下記のようにしています。

```
update
upgrade

# ....

cleanup
```

これはそのままの意味ですが、homebrew の formula の更新とインストール済みパッケージをクリアしてるのに利用されています。

## install

### GitHubとか使うのに便利なやつ

#### git

git の version が新しいのを使いたいので homebrew でいれちゃう

#### hub

hub コマンドをつかって `hub pull-request` とか出来るので是非使いたい

- https://github.com/github/hub

#### tig

gitで色々出来るので入れておくと幸せになれる

- [tigでgitをもっと便利に！ addやcommitも - Qiita](http://qiita.com/suino/items/b0dae7e00bd7165f79ea)


### エディタとかコンソールまわり

#### vim or emacs

だいたいどっちかを入れるんじゃないですかね。version 新しいやつ。

- http://www.vim.org/
- http://www.gnu.org/software/emacs/

#### tmux

screenでも良いかもしれませんが好みで。

- 参考
  - https://github.com/luckypool/dotfiles/blob/master/.tmux.conf

#### zsh, zsh-completions

他のシェルが良いひとならば無理に入れる必要はありません。
インストールしたら `chsh` しましょう。

- completions まわりの設定
  - https://github.com/luckypool/dotfiles/blob/master/.zshrc.osx
- あわせてインストールしたい
  - https://github.com/robbyrussell/oh-my-zsh


# for build ruby
install openssl
install readline

### 便利ツール

#### jq

curl で返ってきたJSONをキレイに表示したい人はこれ使いましょう

- http://stedolan.github.io/jq/

#### nkf

文字コードまわりで困ったらこれを使いましょう

- http://sourceforge.jp/projects/nkf/
- よく使うのは
  - `nkf -g target_file` ← 文字コードの推測
  - `nkf -w --overwrite target_fike` ←　utf で上書き

#### tree

ディレクトリとかの階層表示したいじゃないですか！！

#### terminal-notifier

`terminal-notifier -message 'foo bar'` 

とかやると通知してくれます。何かと捗るかもしれないよ！

### Rubyをビルドする前に

これら使うのでいれておく

#### openssl

暗号化とかするならつかうはず

- http://docs.ruby-lang.org/ja/2.1.0/library/openssl.html

#### readline

- http://docs.ruby-lang.org/ja/2.1.0/class/Readline.html

## cask

[homebrew-cask](https://github.com/phinze/homebrew-cask) でインストールする .dmg とかです

下記のところに一覧があるので、お好みで追加するのが良いと思います。

- https://github.com/phinze/homebrew-cask/tree/master/Casks


### Androidの開発環境

#### java

jdkが入りますよ

- http://www.oracle.com/technetwork/java/javase/downloads/index-jsp-138363.html
- https://github.com/phinze/homebrew-cask/blob/master/Casks/java.rb

#### android-studio

そろそろEclipseじゃなくてこっちですかね。

- http://developer.android.com/sdk/installing/studio.html
- https://github.com/phinze/homebrew-cask/blob/master/Casks/android-studio.rb

#### genymotion

こっち使うほうがサクサク動きますからね

- http://www.genymotion.com/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/genymotion.rb

#### virtualbox

genymotionだったりvagrant使うのには必要です。

- https://www.virtualbox.org/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/virtualbox.rb


### 開発ツールとか

#### google-chrome

- http://www.google.co.jp/intl/ja/chrome/browser/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/google-chrome.rb

#### iterm2

Terminal.app使わない人はこれを。

- http://www.iterm2.com/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/iterm2.rb

#### kobito

スニペットを書くのにはこれで！そして書いたら [Qiita](http://qiita.com/) に投稿しよう！

- http://kobito.qiita.com/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/kobito.rb

#### limechat

無難なIRCクライアント

- http://limechat.net/mac/ja.html
- https://github.com/phinze/homebrew-cask/blob/master/Casks/limechat.rb

#### sublime-text

何かと捗るテキストエディタ

- http://www.sublimetext.com/2
- https://github.com/phinze/homebrew-cask/blob/master/Casks/sublime-text.rb

#### vagrant

手元で環境を気軽に up したいじゃないですか。

- http://www.vagrantup.com/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/vagrant.rb


### ユーティリティとか

### appcleaner

便利アンインストーラー

- http://appcleaner.softonic.jp/mac
- https://github.com/phinze/homebrew-cask/blob/master/Casks/appcleaner.rb

### bettertouchtool

特定のジェスチャーをショートカットキーに登録できる

- http://blog.boastr.net/downloads-secondbar-bettertouchtool-2/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/bettertouchtool.rb

### keyremap4macbook

cmd を 「かな／カナ」に対応させるとかできる。便利。

- https://pqrs.org/macosx/keyremap4macbook/index.html.ja
- https://github.com/phinze/homebrew-cask/blob/master/Casks/keyremap4macbook.rb

### xtrafinder

Finderのウィンドウをタブ化できたりする

- http://www.trankynam.com/xtrafinder/
- https://github.com/phinze/homebrew-cask/blob/master/Casks/xtrafinder.rb
