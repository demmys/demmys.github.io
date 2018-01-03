# Spring Bootを知る

Kotlin + Spring Framework + Spring BootでREST APIサーバを構築するのがイケてるにおいがするので調べる。

## いい感じのページ

* [Spring Initializr](https://start.spring.io/)
  * Spring Bootを使ったアプリケーションのひな型(build.gradleなど)を作れるツール
* [Gradle を始めてみよう](https://qiita.com/3bch/items/639bc0a4afaa7c79a124)
  * Gradleの基本的な書き方についてわかりやすく説明されている
* [Spring Boot 使い方メモ](https://qiita.com/opengl-8080/items/05d9490d6f0544e2351a)
  * 最小限のSpring Boot Webアプリケーションについて、アノテーションの詳細までわかりやすく説明されている
* [Spring MVCのコントローラでの戻り値いろいろ](https://qiita.com/tag1216/items/3680b92cf96eb5a170f0)
  * Spring MVCのコントローラで使えるレスポンスの指定の仕方についてわかりやすく説明されている
* [Spring MVC(+Spring Boot)上での静的リソースへのアクセスを理解する](https://qiita.com/kazuki43zoo/items/e12a72d4ac4de418ee37)
 * サーブレットについてわかりやすく説明されている
* [Kotlin + Spring BootでREST APIを作ってみる](https://qiita.com/ARBALEST000/items/0e0ef5074ae110120ac7)
 * Swagger UIをSpring BootのWebアプリケーションでサーブする方法についてわかりやすく説明されている
 * 実際に使用するには別途[Spring Bootでwebjarのパスを捌けるようにする](#Spring Bootでwebjarのパスを捌けるようにする)設定が必要
* [Spring FrameworkのControllerの基本的なアノテーション](http://morizyun.github.io/java/spring-framework-controller-annotation.html)
 * コントローラで使用される基本的なアノテーションについてわかりやすく説明されている

## Tips

### Spring Bootでwebjarのパスを捌けるようにする

以下のようなWeb.ktファイルを作成するとリソースハンドラにwebjarsへのハンドラを追加できる。

```java
package com.exsample.sample.config

import org.springframework.context.annotation.Configuration
import org.springframework.web.servlet.config.annotation.ResourceHandlerRegistry
import org.springframework.web.servlet.config.annotation.WebMvcConfigurerAdapter
import org.springframework.web.servlet.resource.GzipResourceResolver

@Configuration
class Web : WebMvcConfigurerAdapter() {
    override fun addResourceHandlers(registry: ResourceHandlerRegistry) {
        registry
            .addResourceHandler("/webjars/**")
            .addResourceLocations("classpath:/META-INF/resources/webjars/")
            .resourceChain(false)
            .addResolver(GzipResourceResolver())
    }
}
```

source: http://hosomi.github.io/gitbook/_book/java/webjars.html

[このページを編集](https://github.com/demmys/demmys.github.io/edit/master/dev/lean_spring_boot.md)
