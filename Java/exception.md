# 例外
想定外のエラーのこと。

Javaでは例外に対する処理が行われているかをコンパイル時に調べる。

クラスによって調べるか調べないかが決まっている。

## 例外を表すクラス
### Error

Errorの例外はコンパイル時にチェックされない。

発生時点で、回復困難。

メモリ不足など

### Exception

Exceptionの例外はコンパイル時にチェックされる。
（RuntimeExceptionはチェックされない）

## エラー
### compile error

### runtime error

### logic error



# 例外処理
例外に備えた処理をすること。

## try-catch
``` Java
try {
  // 例外を送る可能性がある処理
} catch (Exception e) {
  // 例外を検知したときの処理
} finally {
  //　例外の有無にかかわらず、tryを実行したら必ず最後に行う処理
}
```

## try-with-resources
``` Java
try (closeする必要があるリソースの宣言) {
  // 例外を送る可能性がある処理
} catch (Exception e) {
  // 例外を検知したときの処理
}
```
try-catchよりtry-with-resourcesを使うほうが、簡潔に書けるケースがある。

## throw
例外を投げるにはthrowを使う。
``` Java
throw 例外クラスのインスタンス;
```
## thrown
例外をそのメソッドではcatchせず呼び出し元に投げる場合にはthrownをメソッド宣言につける
``` Java
public static void method() thrown Exception {
  //　Exceptionが発生しそうな処理

  // thrownで宣言しているのでcatchする必要はない
}
```

