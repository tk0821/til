# 文字列操作

### 生成
``` Java
// Stringオブジェクトの生成

// 文字列リテラルで初期化
String str1 = "aaaaa";

// コンストラクタ
// Stringを渡す
String str2 = new String("bbbbb");

// char型配列を渡す
char[] c = { 'c', 'c', 'c', 'c', 'c' };
String str3 = new String(c); 

// StringBuilder引数を渡す
StringBuilder sb = new StringBuilder();
sb.append("ddddd");
String str4 = new String(sb);

// valueOfメソッド
char[] ch = {'a', 'b', 'c'};
String str5 = String.valueOf(ch);
```

### 比較
```Java
public static void main(String[] args) {
	String str1 = "hello";
	String str2 = "HELLO";

	System.out.println(str1.equals(str2)); // false
	System.out.println(str1.equals("hello")); // true
	System.out.println(str1.equalsIgnoreCase(str2)); // true

  //辞書順で比較する。負の値なら引数より小さい、0なら等しい、正なら引数より大きい
	System.out.println(str1.compareTo(str2)); // 32
	System.out.println(str1.compareToIgnoreCase(str2)); // 0
}
```
Javaの文字列は不変であるため、不要な生成を避けるためにコンスタントプールと呼ばれる定数を記憶するためのメモリに格納される。

以降に、同じ文字列を生成する場合、コンスタントプールに文字列が記憶されているため、同じ参照になる。

internメソッドはコンスタントプールに文字列があるかを確認しあればその文字列、なければプールに追加しこの文字列オブジェクトを返す。

```Java
public class Main {
	public static void main(String[] args) {

		String str1 = "hoge";
		String str2 = "hoge";
		String str3 = new String("hoge");

		System.out.println(str1 == str2); //true
		System.out.println(str1.equals(str2)); //true
		System.out.println(str1 == str3); //false
		System.out.println(str1.equals(str3)); //true
		System.out.println(str1.intern() == "hoge"); //true
		System.out.println(str1.intern() == str2.intern()); //true
		System.out.println(str1.intern() == str3.intern()); //true
	}
}
```

### 長さ
```Java
public static void main(String[] args) {
	String str1 = "hello";
	String str2 = "";

	System.out.println(str1.length()); // 5
	System.out.println(str1.isEmpty()); // false

	System.out.println(str2.length()); // 0
	System.out.println(str2.isEmpty()); // true
}
```

### 検索
``` Java
public static void main(String[] args) {
	String str1 = "hellolleh";
	String str2 = "hoge";

	System.out.println(str1.contains("hello")); // true
	System.out.println(str2.contains("hello")); // false

	System.out.println(str1.startsWith("hello")); // true
	System.out.println(str1.endsWith("hello")); // false

	System.out.println(str1.indexOf("ll")); // 2
	System.out.println(str1.lastIndexOf("ll")); // 5

}
```

### 切り出し
``` Java
public static void main(String[] args) {
	String str1 = "hellolleh";

	System.out.println(str1.charAt(4)); // o
	System.out.println(str1.substring(4)); // olleh
}
```

### 変換
``` Java
public static void main(String[] args) {
	String str1 = "    Hello    ";

	System.out.println(str1.toLowerCase()); // hello
	System.out.println(str1.toUpperCase()); // HELLO
	System.out.println(str1.trim()); // Hello
	System.out.println(str1.replace("ll", "LL")); // HeLLo
}
```

# StringBuilder
文字列の連結は＋演算子よりもStringBuilderを使うほうが高速。

＋演算子は連結するごとにnewで新たなStringを生成している。

```Java
StringBuilder sb = new StringBuilder();
sb.append("abc").append("def").append("ghi");
System.out.println(sb.toString()); // abcdefghi
```
appendを連続して呼び出すような書き方をメソッドチェーンという。

# format
書式指定文字列をつかって文字列を扱える。
cでいうprintf。
```Java
String str = String.format("%d", 10);
System.out.println(str); // 10

System.out.printf("%d", 10); // 10
```

