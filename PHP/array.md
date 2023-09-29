# array

```php
$x[0] = "aaa";
$x[1] = "bbb";

$y = array("aaa", "bbb");
$y[] = "ccc";
```
```php
$x = array(
  //key => value
  "aaa" => "1",
	"bbb" => "222",
	"ccc" => "55555",
);

$x = [
  //key => value
  "aaa" => "1",
	"bbb" => "222",
	"ccc" => "55555",
];


echo $x["aaa"]; // 1
```

# sort
``` php
sort($array);  // valueを昇順でソート。keyは消去され新たに割り振られる
rsort($array); // valueを降順でソート

ksort($array); // keyを昇順でソート
krsort($array);// keyを降順でソート

asort($array); // valueを昇順でソート。keyは保持される
arsort($array);// valueを降順でソート
```
