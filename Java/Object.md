# Objectクラス
Javaにおいて、すべてのクラスの親。

クラス定義時に、継承の指定がなければjava.lang.Objectを継承したとみなされる。

このクラスにtoStringメソッドやequalsメソッドが定義されている。

### equals
Objectで定義されているequalsメソッドは等値であるかを判定している。

この関数をオーバーライドする場合、hashcodeメソッドも適切にオーバーライドする必要がある。

