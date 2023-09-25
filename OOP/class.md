# クラス
クラスはインスタンスを作るためのひな型として考えることができる。

クラスに含まれるフィールドとメソッドをメンバという。

クラスをわかりやすく図示したクラス図というものがある。
クラス図はUMLで定められている。

DogはAnimalを継承している。
``` mermaid
classDiagram
  Animal <|-- Dog
  class Animal {
		+int age
		+String gender
    +eat()
    +sleep()
	}

  class Dog {
    +bark()
  }
```
以下クラス図はHumanはSwordを持っている。

has-aの関係がある。
``` mermaid
classDiagram
  Human o-- Sword
  class Human {
		+String name
		+int hp
    +Sword sword
    +attack()
	}

  class Sword {
    +String name
    +int attack;
  }
```
