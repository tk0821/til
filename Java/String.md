# 文字列操作

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

