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


