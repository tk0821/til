## if
```php
if ($x > 0) {
	echo "x > 0";
} elseif ($x < 0) {
	echo "x > 0";
} else {
	echo "x == 0";
}
```
elseifとelse ifの書き方ができる。


また、コロンを使った記法もある。この場合はelse ifは使えない。
```php
if ($x > 0) :
	echo "x > 0";
elseif ($x < 0) :
	echo "x > 0";
else :
	echo "x == 0";
endif;
```
