# 継承
``` Java
public class Animal {
  public void sleep() {
    System.out.println("寝ます");
  }
}

public class Dog extends Animal {
  public void sleep() {
    System.out.println("寝るワン");
  }
}
```
extendsを使ってクラスの継承ができる。

スーパークラスで宣言されたメソッドをサブクラスでオーバーライドできる。

##　継承、オーバーライドの禁止
クラスやメソッドの宣言にfinalをつけることで継承、オーバーライドを禁止できる。
``` Java
public final class Animal {
  public void sleep() {
    System.out.println("寝ます");
  }
}

/* 継承できない
 * public class Dog extends Animal {
 *    ...
 *  }
 */
```

``` Java
public class Animal {
  public final void sleep() {
    System.out.println("寝ます");
  }
}

public class Dog extends Animal {
  /* オーバーロードできない
   * public void sleep() {
   *   System.out.println("寝るワン");
   * }
   */
}
```

## サブクラスからスーパークラスのメンバを呼び出す
superを使うことでスーパークラスのメンバを呼び出せる。
``` Java
public class Animal {
  public void sleep() {
    System.out.println("寝ます");
  }
}

public class Dog extends Animal {
  public void sleep() {
    //寝ます
    super.sleep();
  }
}
```

## コンストラクタ
サブクラスのコンストラクタではスーパークラスのコンストラクタを呼び出さなければならない。

スーパークラスのコンストラクタを呼び出すにはsuper()を使用する。

サブクラスのコンストラクタにスーパークラスのコンストラクタがない場合、
``` Java
super();
```
上記の命令が自動的に追加され、コンストラクタが呼び出される。

スーパークラスのコンストラクタが引数を必要とする場合、サブクラスでスーパークラスのコンストラクタを明示的に呼び出す必要がある。

# メモ

フィールドへのアクセスはインスタンスの変数の型で判断される。

オーバーライドしているメソッドを呼び出す場合、オーバーライドしたクラスのフィールドを呼び出す。

``` java
class Main {
  public static void main(String[] string) {
    A a = new A();
    A b = new B();
    A c = new C();
    B b2 = new B();
    C c2 = new C();

    a.test();  // 10
    b.test();  // 20
    c.test();  // 10
    b2.test(); // 20
    c2.test(); // 10

    System.out.println(a.x);  // 10
    System.out.println(b.x);  // 10
    System.out.println(c.x);  // 10
    System.out.println(b2.x); // 20
    System.out.println(c2.x); // 30
  }
}

class A {
  final int x;
  { x = 10; }

  public void test() { System.out.println(x); }
}

class B extends A {
  final int x;
  { x = 20; }

  @Override
  public void test() {
    System.out.println(x);
  }
}

class C extends A {
  final int x;
  { x = 30; }
}
```
