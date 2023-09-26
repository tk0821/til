# 継承
あるクラスのフィールドやメソッドをベースにしてほかのクラスを作ること。

例）

動物というクラスを継承して、犬というクラスを作る。

乗り物というクラスを継承して、車というクラスを作る。

``` mermaid
classDiagram
  Animal <|-- Dog
  class Animal {
    + int age
    + String name
    + sleep()
  }
  class Dog {
    + String dogBreed
    + bark()
  }

  Vehicle <|-- car
  class Vehicle {
    + String color
    + move()
  }
  class car {
    + String carModel
  }
```

継承元のクラスをスーパークラス（親クラス）と呼び、

継承先のクラスをサブクラス（子クラス）と呼ぶ。

## オーバーライド
継承したメソッドの動作をサブクラスで上書きすることをオーバーライドという。

## is-aの関係
継承の関係はスーパークラスをA、サブクラスをBとしたときに「B is-a A」の関係が成立すると良いとされる。

この関係が成立するとき、BはAのサブタイプである。

継承は「is-a」関係を必ず満たしているわけではない。

## 汎化と特化
継承元のクラスほど抽象的に汎化し、継承先のクラスほど具体的に特化していく。

