# Spring Boot
Spring Bootとは、Spring Frameworkを使ったアプリケーションを簡単に作ることができるフレームワーク。

Spring Bootの規約を守ることでほとんどのSpringの設定が不要になる。

Spring Frameworkは多くの選択肢を与えるが、その分設定ファイルの記述が大変なのでSpring Bootを使ってその手間を省く。

#  プロジェクト構成
Spring Bootのプロジェクト構成(EclipseのSpringスタータープロジェクト)の中をいくつか確認する。

`src/main/java`

javaファイルを配置する。このディレクトリ内のパッケージにメインメソッドが記述されたApplication.javaがある。

`src/main/resources`

HTML, CSSなどプログラム実行時に使用するclassファイル以外のファイルを配置する。

`src/test/java`

テスト用のjavaファイルを配置する。

# @SpringBootApplication
`@EnableAutoConfiguration`, `@SpringBootConfiguration`, `@ComponentScan`を組み合わせたアノテーション。

このアノテーションによってSpring Bootとして実行できるようになる。

### メモ
Spring Bootとしての機能は@SpringBootApplicationアノテーションを付与して簡単に実行できるようにすることっぽい。

コードを書いていくときはSpring Frameworkについて調べる必要がありそう。
