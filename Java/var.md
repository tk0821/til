# var
ローカル変数の型推論という機能によって、型名をvarに置き換えて変数を宣言することで、初期値から推論した型を当てはめてくれる。

``` Java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    var i = 1000;
    var l = 100_000_000_000L;
    var ch = 'a';
    var bool = true;

    var str = "abcde";
    var list = new ArrayList<>();

    // プリミティブ型はキャストしてラッパークラス名を取得する
    System.out.println(((Object)i).getClass().getSimpleName());
    System.out.println(((Object)l).getClass().getSimpleName());
    System.out.println(((Object)ch).getClass().getSimpleName());
    System.out.println(((Object)bool).getClass().getSimpleName());

    System.out.println(str.getClass().getSimpleName());
    System.out.println(list.getClass().getSimpleName());
  }
}
```
```
> java .\Main.java
Integer
Long
Character
Boolean
String
ArrayList
```
