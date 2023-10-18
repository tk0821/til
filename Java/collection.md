
データ構造を扱うクラスをコレクションフレームワークという。

# Collection
コレクションのインターフェース。

コレクションは2つのコンストラクタが必要。

+ 空のコレクションを作成する引数なしのコンストラクタ
+ Collection型の引数を1つ受け取り、同じ要素で新しくコレクションを作成するコンストラクタ

提供しているメソッドでoptionでなく、使いそうなものを一部記載

|提供されているメソッド|説明|
|--------------------|------------------|
|contains(Object o)|oがコレクションに含まれているか|
|containsAll<Collection ?> c)|cのすべての要素がコレクションに含まれているか|
|equals(Object o)|oとコレクションが等しいか|
|isEmpty()|コレクションに要素がないか|
|removeIf(Predicate<? super E> filter)|条件を満たすコレクションの要素をすべて削除|
|size()|コレクションの要素の数|
|toArray()|コレクションの要素がすべて含まれる配列を返す|

# List
データを並べて格納するデータ構造のインターフェース

|提供されているメソッド|説明|
|--------------------|------------------|
|copyOf(Collection<? extends E> c)|cの要素を含む変更不可能なリストを返す静的メソッド|
|of()|空の変更不可能なリストを返す静的メソッド|
|of(E e)|eを含む変更不可能なリストを返す静的メソッド|
|of(E... e)|eを含む変更不可能なリストを返す静的メソッド|


## ArrayList
``` Java
import java.util.ArrayList;

ArrayList<String> names = new ArrayList<String>();

names.add("aaa");
names.add("bbb");

System.out.println(names.get(1)); // aaa
```

## LinkedList
連結リスト

各要素が並んでいない。

挿入・削除が速く、指定位置の要素の取得が遅い。


### イテレータ
リストの中身を１つずつ取り出すための方法の１つ
``` Java
Iterator<String> it = list.iterator();

While (it.hasNext()) {
  String e = it.next();
}
```

# Set
複数の情報を重複なく格納するsetというデータ構造。

一般的にhashSetが使われる。

# Map

2つのデータをkeyとvalueのペアとして格納するデータ構造。

keyは重複しない。

``` Java
Map<String, int> map = new HashMap<String, int>();

for (String key : map.keySet()) {
  int value = map.get(key);
}
```

# ラッパー
コレクションの要素の型に基本型を使えないかわりに、基本型を保持するラッパークラスを使う。

Integer, Doubleなど

