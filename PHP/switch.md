# switch
``` php
switch ($x) {
	case 1:
		echo "x==1";
		break;
	case 2:
		echo "x==2";
		break;
	default:
		echo "default";
}
```

switch文において、continueはbreakと同じ処理が行われる。

ループから抜けるためにはcontinue 2を使う。
```php
for ($i = 1; $i <= 3; $i++) {
	switch ($x) {
		case 1:
			echo "x==1";
			continue;  //Warning: "continue" targeting switch is equivalent to "break". Did you mean to use "continue 2"?
		case 2:
			echo "x==2";
			continue 2;
		default:
			echo "default";
	}
}
```
