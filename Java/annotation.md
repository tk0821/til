# アノテーション
プログラムに記述する注釈のこと。

コードにメタデータを追加することができる。

## 種類
+ マーカーアノテーション
  値を持たない名前だけのアノテーション
+ 単一値アノテーション
  値を1つだけもつアノテーション
+ フルアノテーション
  値を複数持つアノテーション

# @Override
このアノテーションはメソッドがスーパークラスのメソッドをオーバーライドしていることを示すマーカーアノテーション。

オーバーライドしていない場合はエラーを発生させる。

```Java
class Main {
  public static void main(String[] args) {
    A a = new A();
    B b = new B();
  }
}

class A {
  public void hello() { System.out.println("Hello!"); }
}

class B extends A {
  @Override
  public void hello2() {
    System.out.println("hello?");
  }
}
```
```
> java .\Main.java
.\Main.java:13: エラー: メソッドはスーパータイプのメソッドをオーバーライドまたは実装しません
  @Override
  ^
エラー1個
エラー: コンパイルが失敗しました
```
オーバーライドしたつもりができていないというミスを防げる。

