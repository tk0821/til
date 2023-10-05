Mathクラスから使いそうなメソッド、フィールドを出力させてみる

```java
public class Main {
  public static void main(String[] args) {
    // Mathクラス　フィールド
    System.out.println(Math.E);  // 2.718281828459045
    System.out.println(Math.PI); // 3.141592653589793

    // abs　絶対値
    System.out.println(Math.abs(-10)); // 10

    // Exact 引数の計算
    System.out.println(Math.addExact(10, 20));      // 30
    System.out.println(Math.subtractExact(10, 20)); // -10
    System.out.println(Math.multiplyExact(10, 20)); // 200

    // 切り上げ切り捨て
    System.out.println(Math.ceil(3.5D));  // 4.0
    System.out.println(Math.floor(3.5D)); // 3.0
    System.out.println(Math.round(3.5D)); // 4

    // 最大最小
    System.out.println(Math.max(10, 20)); // 20
    System.out.println(Math.min(10, 20)); // 10

    // 平方根
    System.out.println(Math.sqrt(4D)); // 2.0

    // 三角関数
    System.out.println(Math.sin(30D)); // -0.9880316240928618
    System.out.println(Math.cos(30D)); // 0.15425144988758405
    System.out.println(Math.tan(30D)); //-6.405331196646276

    // ランダムなdouble
    System.out.println(Math.random()); // 0.06955992036813241
  }
}
```
