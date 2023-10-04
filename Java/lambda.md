# 関数型インターフェース
実装が必要な抽象メソッドを1つだけ持っているインターフェースのことを関数型インターフェースという。

java.util.functionにまとまって定義されている。

# ラムダ式

関数型インターフェースのメソッドを簡潔に定義するための方法。

ローカルクラスや無名クラスをさらに短く書ける。

``` java
import java.util.function.Consumer;

public class Main {
  public static void main(String[] args) {
    Consumer<String> c = (str) -> System.out.println(str);
    c.accept("hello");
  }
}
```
出力
```
hello
```

Consumerは引数を1つ受け取って戻り値を返さない動作を行う。
ここでは、画面に出力させる動作を実装。
