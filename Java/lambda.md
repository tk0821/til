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
    Consumer<String> c = (str) -> System.out.println(str); // hello
    c.accept("hello");
  }
}
```

Consumerは引数を1つ受け取って戻り値を返さない動作を行う。
ここでは、画面に出力させる動作を実装。

## ローカル変数との関係
ラムダ式でローカル変数にアクセスする場合、ラムダ式で値を変更できない。
```Java
public static void main(String[] string) {
  int a = 10;
  Test t1 = () -> { System.out.println(a); };  // 値を変更しないのでローカル変数にアクセスできる
  Test t2 = () -> { System.out.println(a++); }; // エラー: ラムダ式から参照されるローカル変数は、finalまたは事実上のfinalである必要があります
  t.test();
}

interface Test {
  void test();
  }
}
```
