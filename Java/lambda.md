# 関数型インターフェース
実装が必要な抽象メソッドを1つだけ持っているインターフェースのことを関数型インターフェースという。

java.util.functionにまとまって定義されている。

# ラムダ式

関数型インターフェースのメソッドを簡潔に定義するための方法。

ローカルクラスや無名クラスをさらに短く書ける。

## 主な関数型インターフェースとラムダ式を使った定義

### Consumer
Consumerは引数を1つ受け取って戻り値を返さない動作を行う。

メソッド名はaccept
``` java
import java.util.function.Consumer;

public class Main {
  public static void main(String[] args) {
    Consumer<String> c = (str) -> System.out.println(str); // hello
    c.accept("hello");
  }
}
```
### Function
Functionは引数を受け取って戻り値を返す動作を行う。

メソッド名はapply
``` java
import java.util.function.Function;

class Main {
  public static void main(String[] string) {
    Function<Integer, String> f = x -> String.valueOf(x) + "が渡されました";
    System.out.println(f.apply(10));  // 10が渡されました
  }
}
```

### Predicate
Predicateは引数を1つ受け取ってbooleanを返す動作を行う。

メソッド名はtest
``` Java
import java.util.function.Predicate;

class Main {
  public static void main(String[] string) {
    Predicate<Integer> p = x -> x % 2 == 0;
    System.out.println(p.test(10)); // true
  }
}
```

### Supplier
Supplierは引数を受け取らず、戻り値を返す動作を行う。

メソッド名はget
```java
import java.util.function.Supplier;

class Main {
  public static void main(String[] string) {
    Supplier<String> s = () -> { return "supplier"; };
    System.out.println(s.get()); // supplier
  }
}
```

## ローカル変数との関係
ラムダ式でローカル変数にアクセスする場合、事実上finalである必要がある。
```Java
public static void main(String[] string) {
  int a = 10;
  Test t1 = () -> { System.out.println(a); };  // 値を変更していなければローカル変数にアクセスできる
  //Test t2 = () -> { System.out.println(a++); }; // エラー: ラムダ式から参照されるローカル変数は、finalまたは事実上のfinalである必要があります
  t.test();

  //ここでaを変更すると事実上finalとは言えないのでラムダ宣言でエラーが発生する
  // a+=1;
}

interface Test {
  void test();
  }
}
```
