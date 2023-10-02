# スーパーグローバル
どこでも使える、PHPにあらかじめ組み込まれた変数

## GET/POST
httpリクエストで渡された変数の連想配列。
```php
$_GET["hoge"];
$_POST["hoge"];
```

## COOKIE
クッキーから渡された変数の連想配列。

クッキーはブラウザに保存される。
```php
setcookie("hoge", "huga", time()+60*60*24*7);
echo $_COOKIE["hoge"];  //huga
```

## SESSION
使用できるセッション変数の連想配列。

セッションはサーバーに保存される。
```php
session_start;  // sessionが有効になる
$_SESSION['hoge'] ="huga"; // 値を保存する
echo $_SESSION['hoge'] // huga
```

```php
session_destroy(); // セッション変数をすべて削除する関数
session_write_close(); //セッションデータを保存し、終了する関数
```

## FILES
postでアップロードされたファイルの連想配列。
```php
// htmlでname="name"でアップロードされた場合、以下の変数を扱える
$_FILES['name']['name']; //ファイル名
$_FILES['name']['type']; //ファイルの型
$_FILES['name']['size']; //サイズ（バイト）
$_FILES['name']['tmp_name']; //アップロードされたファイル名（tmpファイル）
$_FILES['name']['error']; // エラーコード
```
