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
