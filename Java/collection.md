
データ構造を扱うクラスをコレクションフレームワークという。

# List
データを並べて格納するデータ構造。
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

