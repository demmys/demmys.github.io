demmy.jp Wiki
=====

便利なツール
-----
* [Web上でクラス図を作成](https://www.planttext.com/)
* [ターミナル用のカラースキーマを作成](http://ciembor.github.io/4bit/#)
* [文字数カウンター](https://demmy.jp/utilities/word_counter.html#!?cs=true)
* [フラットデザインっぽいカラーパレット](http://flatuicolors.com/)
* [半角英数字を全角に変換](https://kujirahand.com/web-tools/ZenHan.php)

Tips
-----
#### macOSの基本的な環境構築
| 用途 | ソフトウェア |
|:--:|:--:|
| トラックパッド機能拡張 | [BetterTouchTool](https://www.boastr.net/) |
| 日本語IME | [Google日本語入力](https://www.google.co.jp/ime/) |
| ターミナルエミュレータ | [iTerm2](https://www.iterm2.com/) |
| ターミナル基本コマンド | [XCode](https://itunes.apple.com/jp/app/xcode/id497799835?mt=12), [Command Line Tools](https://developer.apple.com/download/more/) |
| パッケージマネージャ | [Homebrew](https://brew.sh/index_ja.html) |
| 言語環境バージョンマネージャ | [anyenv](https://github.com/riywo/anyenv) |
| パッケージマネージャ | [Homebrew](https://brew.sh/index_ja.html) |
| Linuxコマンド | `brew install wget tree` |
| 起動設定 | [dotfiles](https://github.com/demmys/dotfiles) |

#### macOSでlua付きのVimをインストール
```bash
$ brew install lua
$ brew install vim --with-lua
$ vim --version | grep lua
+cursorshape       +lua               +ruby              -X11
```

#### Ubuntuでlua付きのVimをインストール
```bash
$ sudo apt-get install vim-gnome
```

#### UbuntuでTmux2.7をインストール
```bash
$ sudo add-apt-repository ppa:pi-rho/dev
```
see: https://launchpad.net/~pi-rho/+archive/ubuntu/dev

#### macOSにJava(JDK)をインストール
```bash
$ brew install caskroom/cask/brew-cask
$ brew cask install java8
$ anyenv install jenv
$ jenv add $(/usr/libexec/java_home -v 1.8)
$ jenv global 1.8
```

#### UbuntuにJava(JDK)をインストール
```bash
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt-get update
$ sudo apt-get install oracle-java8-installer
$ anyenv install jenv
$ jenv add /usr/lib/jvm/java-8-oracle/
$ jenv global 1.8
```

#### UbuntuにKotlinをインストール
```bash
curl -s "https://get.sdkman.io" | bash
sdk install kotlin
```
see: http://sdkman.io/index.html

#### Ubuntu aptパッケージの検索
https://launchpad.net/

#### Ubuntu PPAの検索
https://launchpad.net/ubuntu/+ppas

#### WSLでpbcopy/pbpasteを使う
```bash
# @Windows
$ cinst pasteboard
# @Ubuntu
$ cat >> ~/.bash_profile
alias pbcopy='pbcopy.exe'
alias pbpaste='pbpaste.exe'
```
see: https://github.com/ghuntley/pasteboard

[このページを編集](https://github.com/demmys/demmys.github.io/edit/master/index.md)
