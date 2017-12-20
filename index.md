demmy.jp Wiki
=====

便利なツール
-----
* [ターミナル用のカラースキーマを作成](http://ciembor.github.io/4bit/#)
* [文字数カウンター](https://demmy.jp/utilities/word_counter.html#!?cs=true)
* [フラットデザインっぽいカラーパレット](http://flatuicolors.com/)
* [半角英数字を全角に変換](https://kujirahand.com/web-tools/ZenHan.php)

Tips
-----

### 開発関連

#### Vim

##### macOSでlua付きのVimをインストール
```bash
$ brew install lua
$ brew install vim --with-lua
$ vim --version | grep lua
+cursorshape       +lua               +ruby              -X11
```

##### Ubuntuでlua付きのVimをインストール
```bash
$ sudo apt-get install vim-gnome
```

#### Tmux

##### Ubuntuで2.7をインストール
```bash
$ sudo add-apt-repository ppa:pi-rho/dev
```
see: https://launchpad.net/~pi-rho/+archive/ubuntu/dev

#### Java

##### macOSにインストール
```bash
$ brew install caskroom/cask/brew-cask
$ brew cask install java8
$ anyenv install jenv
$ jenv add $(/usr/libexec/java_home -v 1.8)
$ jenv global 1.8
```

##### Ubuntuにインストール
```bash
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt-get update
$ sudo apt-get install oracle-java8-installer
$ anyenv install jenv
$ jenv add /usr/lib/jvm/java-8-oracle/
$ jenv global 1.8
```

#### Kotlin

##### macOSにインストール
```bash
brew install kotlin
```

##### Ubuntuにインストール
```bash
curl -s "https://get.sdkman.io" | bash
sdk install kotlin
```

#### Ubuntu

##### aptitudeパッケージの検索
https://launchpad.net/

##### PPAの検索
https://launchpad.net/ubuntu/+ppas

#### Windows Subsystem for Linux

##### pbcopy/pbpaste
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
