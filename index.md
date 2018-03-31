demmy.jp Wiki
=====

開発
-----
* [Spring Bootを知る](dev/lean_spring_boot.md)

娯楽
-----
* [ゴキブリポーカーロイヤルのルール](game/cockroach_poker_royal.md)

便利なツール
-----
* [Web上でクラス図を作成](https://www.planttext.com/)
* [ターミナル用のカラースキーマを作成](http://ciembor.github.io/4bit/#)
* [文字数カウンター](https://demmy.jp/utilities/word_counter.html#!?cs=true)
* [フラットデザインっぽいカラーパレット](http://flatuicolors.com/)
* [半角英数字を全角に変換](https://kujirahand.com/web-tools/ZenHan.php)
* [適当なサイズのサンプル画像を用意](http://placekitten.com/)
* [GitHubで使える絵文字の一覧](https://www.webpagefx.com/tools/emoji-cheat-sheet/)

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
| Linuxコマンド | `brew install wget tree rlwrap` |
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
$ curl -s "https://get.sdkman.io" | bash
$ sdk install kotlin
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

#### macOSでnginx+php-fpmを構築
phpenvでインストールした場合はphp-fpmも一緒にビルドされている
```bash
$ brew install nginx
$ cd $(dirname $(phpenv which php-fpm))/..
$ cp etc/php-fpm.conf.default etc/php-fpm.conf
$ vim etc/php-fpm.conf
$ diff etc/php-fpm.conf.default etc/php-fpm.conf
17c17
< ;pid = run/php-fpm.pid
---
> pid = run/php-fpm.pid
81c81
< ;daemonize = yes
---
> daemonize = yes
$ cp etc/php-fpm.d/www.conf.default etc/php-fpm.d/www.conf
$ cat > $HOME/Library/LaunchAgents/phpenv.php-fpm.plist
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
    <dict>
        <key>Label</key>
        <string>phpenv.php-fpm.7.1.9</string>
        <key>RunAtLoad</key>
        <true/>
        <key>KeepAlive</key>
        <false/>
        <key>ProgramArguments</key>
        <array>
            <string>$YOUR_HOME/.anyenv/envs/phpenv/versions/$YOUR_PHP_VERSION/sbin/php-fpm</string>
            <string>--nodaemonize</string>
        </array>
    </dict>
</plist>
$ launchctl load $HOME/Library/LaunchAgents/phpenv.php-fpm.plist
$ cat > /usr/local/etc/nginx/servers/php-fpm
~~~
$ brew services nginx start
```

#### macOSでsshfsを利用
```bash
$ brew tap caskroom/cask
$ brew install caskroom/cask/osxfuse sshfs
```

#### macOSでLISTENしているTCPポートの情報を表示
```bash
$ lsof -nP -iTCP -sTCP:LISTEN
```

#### GitHubの二段階認証を有効化した状態でhttpsでpushするためのトークンを生成
https://github.com/settings/tokens

[このページを編集](https://github.com/demmys/demmys.github.io/edit/master/index.md)
