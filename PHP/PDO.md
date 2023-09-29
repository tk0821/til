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
