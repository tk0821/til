# java.time
時間を扱うAPI

すべてのクラスはimmutableでスレッドセーフ。

## prefix
このAPIではメソッド名に以下の接頭辞が使われている。

|接頭辞|意味|
|-------|---------|
|of|staticなファクトリメソッド。インスタンスを生成する。|
|parse|parseした値で生成する、staticなファクトリメソッド。|
|get|ある値を取得する。|
|is|trueかどうか調べる。|
|with|実質setter。値で置き換えた新たなオブジェクトを生成しそのコピーを返す。|
|plus|値を足す。|
|minus|値を引く。|
|to|このオブジェクトの型を変換する。|
|at|このオブジェクトと別のオブジェクトを結合させる。|

# Instatnt
ある時点を表す。タイムスタンプとか。
``` java
import java.time.Instant;

class Main {
  public static void main(String[] string) {
    System.out.println(Instant.EPOCH); // UNIX時間

    Instant time = Instant.now();              // 現在のインスタント
    System.out.println(time.getEpochSecond()); // インスタントのUNIX時間

    Instant time2 =
        time.minusSeconds(100000); // timeから100000秒引いたインスタント
    System.out.println(time2.getEpochSecond()); // time2インスタントのUNIX時間

    Instant time3 =
        Instant.ofEpochSecond(1680000000); // ファクトリメソッドで生成する
    System.out.println(time3.getEpochSecond()); // time3インスタントのUNIX時間
  }
}
```
```bash
> java .\Main.java
1970-01-01T00:00:00Z
1697163312
1697063312
1680000000
```

# LocalDate
タイムゾーンのない日付。

```java
import java.time.LocalDate;

class Main {
  public static void main(String[] string) {
    System.out.println(LocalDate.EPOCH);

    LocalDate time = LocalDate.now();
    System.out.println(time);

    LocalDate time2 = LocalDate.of(2023, 10, 13);
    System.out.println(time.equals(time2));

    LocalDate time3 = LocalDate.parse("2023-10-13");
    System.out.println(time.equals(time3));

    LocalDate time4 = time.withMonth(1);
    time.withMonth(12); // immutableなので値を書き換えていない
    System.out.println(time);
    System.out.println(time4);
  }
}
```
```bash
> java .\Main.java
1970-01-01
2023-10-13
true
true
2023-10-13
2023-01-13
```
