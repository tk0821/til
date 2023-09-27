# 静的メンバ

staticがついているメンバを静的メンバという。

```Java
static int x;
```

### 特徴
・実体はクラスに1つだけある
・各インスタンスから呼び出せる

```Java
class A {
	static int x;
}

class Main {
	public static void main(String[] args) {
		A a1 = new A();
		A a2 = new A();

		a1.x = 10; //The static field A.x should be accessed in a static wayJava(570425420)
		a2.x = 20; //The static field A.x should be accessed in a static wayJava(570425420)
    
		A.x = 30;

		System.out.println(a1.x);  // 30
		System.out.println(a2.x);  // 30
		System.out.println(A.x);   // 30
	}
}

```
仮にフィールドにアクセスしたい場合は、クラスからアクセスが良い。

基本的にはstatic finalで定数を扱う。

# 静的メソッド
staticがついているメソッドを静的メソッドという。

### 特徴
・メソッドはクラスから呼び出せる
・インスタンスは不要
・同一クラス内のstaticがついていないメンバを利用できない

``` Java
class A {
  String str = "HELLO";

	static void hello() {
		System.out.println("hello");

    // Cannot make a static reference to the non-static field str
    // System.out.println(str);  
	}
}

class Main {

	public static void main(String[] args) {
		A a = new A();

		a.hello(); // The static method hello() from the type A should be accessed in a static wayJava(603979893)
		A.hello();
	}
}
```
