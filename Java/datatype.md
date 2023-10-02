ラッパー型に最大、最小、サイズを保持する定数が定義されている。

整数型を表示させる。

## コード
```java
public class Main {
	public static void main(String[] args) {
		System.out.println("byte");
		System.out.println("  max: " + Byte.MAX_VALUE);
		System.out.println("  mix: " + Byte.MIN_VALUE);
		System.out.println(" size: " + Byte.SIZE + "byte");

		System.out.println("-------------------------------");
		System.out.println("short");
		System.out.println("  max: " + Short.MAX_VALUE);
		System.out.println("  mix: " + Short.MIN_VALUE);
		System.out.println(" size: " + Short.SIZE + "byte");

		System.out.println("-------------------------------");
		System.out.println("int");
		System.out.println("  max: " + Integer.MAX_VALUE);
		System.out.println("  mix: " + Integer.MIN_VALUE);
		System.out.println(" size: " + Integer.SIZE + "byte");
		
		System.out.println("-------------------------------");
		System.out.println("long");
		System.out.println("  max: " + Long.MAX_VALUE);
		System.out.println("  mix: " + Long.MIN_VALUE);
		System.out.println(" size: " + Long.SIZE + "byte");
	}
}
```
## 出力
```
byte
  max: 127
  mix: -128
 size: 8byte
-------------------------------
short
  max: 32767
  mix: -32768
 size: 16byte
-------------------------------
int
  max: 2147483647
  mix: -2147483648
 size: 32byte
-------------------------------
long
  max: 9223372036854775807
  mix: -9223372036854775808
 size: 64byte
```
# 最大より大きい値を代入してみる

``` Java
public class Main {
	public static void main(String[] args) {
		byte b = 128;
		short s = 32768;
		int i = 2147483648;
		long l = 9223372036854775808;
	}
}
```
```
Main.java:5: エラー: 整数が大きすぎます。
                int i = 2147483648;
                        ^
Main.java:6: エラー: 整数が大きすぎます。
                long l = 9223372036854775808;
                         ^
エラー2個
エラー: コンパイルが失敗しました
```
intとlongでエラーを検知した。

これら2つの文をコメントアウトしてみる。

```Java
public class Main {
	public static void main(String[] args) {
		byte b = 128;
		short s = 32768;
		//int i = 2147483648;
		//long l = 9223372036854775808;
	}
}
```
```
Main.java:3: エラー: 不適合な型: 精度が失われる可能性があるintからbyteへの変換
                byte b = 128;
                         ^
Main.java:4: エラー: 不適合な型: 精度が失われる可能性があるintからshortへの変換
                short s = 32768;
                          ^
エラー2個
エラー: コンパイルが失敗しました
```

byte, shortでエラーを検知した。

検知されるエラーに優先順位があるが、どれもコンパイルエラーが発生する。
