# PDO
データベースと接続するためのクラス
```php

$pdo = new PDO(dsn, user, pw);

```
exec()やquery()でSQL文を実行する。
```php

$pdo->exec("sql文;");
$pdo->query("sql文");

```

# プリペアードステートメント
実行したいSQL文の型を先に準備すること。

## メリット
- 高速に動作する
- SQLインジェクション対策

## 例
```php
$pdo = new PDO(dsn, user, pw);
$stmt = $pdo->prepare("insert into table_name(name, mail, password, picture, comments) values(?,?,?,?,?)");

$stmt->bindValue(1, $_POST['name']);
...
$stmt->bindValue(1, $_POST['comments']);

$stmt->execute();
$pdo=NULL;
```
