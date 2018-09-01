20180901 - 認証・認可サーバを作る
=====

## 概要
Node.js + express.jsで認証・認可サーバを作る方法について調べる。
要件は以下。

* アプリからのAPIリクエストの認証・認可ができること
* 認証と同時にユーザー識別子を取得できること
* Google Accountなど外部サービスのOpenIDをパスワード認証の代わりに使用できること
* 初期はアプリ内に保存した自動生成のIDとパスワードで認証できること

興味はあるけど現時点ではいらなそうな機能は以下。

* 2段階認証
* Touch IDなどの生体認証をパスワード認証の代わりに使用

## 認証の構成
パスワード認証をベースとしたOpen ID Connectでできる気がする。
3種類のユーザー認証が必要になりそう。

* アプリユーザー認証 (userid)
  * アプリを使うユーザ一人一人を識別するためのもっとも重要な認証
  * useridで識別
  * 基本はパスワード認証
  * 外部サービス連携した場合はそのサービスのOpenIDをパスワードの代わりに使用できる
  * 認証後に独自のOpen IDを発行して権限を引き回す
* アプリ認証 (appid)
  * 自分が発行したアプリであることを証明する認証と認可が一緒になったID
  * 管理者用画面でsecretと一緒に発行
  * これいつ認証するんだ...?
* 管理者認証 (adminid)
  * appidの発行などを行えるユーザーの認証
  * Google AccountのOpenIDで認証
  * IDはメールアドレスでよさそう

## サーバの構成
* gateway
  * access tokenの解決・JWTの発行
  * 各APIへのプロキシ
* userfe
  * ログイン画面の提供
* userpf
  * access tokenの発行
  * ユーザ情報の管理
  * ユーザー情報設定APIの提供

fe, app -> gateway -> pf

## 使えそうな情報
* OAuth2ならいい感じにできるらしい
  * [【Node.js】expressでOAuth2プロバイダーを作ろう](https://qiita.com/seapolis/items/5f866e58784baf54f54c)
  * [express-oauth-server](https://www.npmjs.com/package/express-oauth-server)
* いい感じにID生成できるライブラリ
  * [nanoid](https://github.com/ai/nanoid)
* Open ID Connectの説明
  * [[前編] IDトークンが分かれば OpenID Connect が分かる](https://qiita.com/TakahikoKawasaki/items/8f0e422c7edd2d220e06#4-json-web-encryption-jwe)
* Open ID Connectサーバライブラリ
  * [Node.jsでOpenID ConnectのOPとRPを実装してみた](https://qiita.com/moomooya/items/97864e1078a3cc204c17)
  * [node-oidc-provider](https://github.com/panva/node-oidc-provider)

[このページを編集](https://github.com/demmys/demmys.github.io/edit/master/dev/20180901_authserver.md)
