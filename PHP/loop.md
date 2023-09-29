# while
``` php
while (条件式) {
  // 処理
}

while (条件式) :
  // 処理
endwhile;
```

# for
``` php
for (ループ開始時に実行される式; 条件式; 各繰り返しの後に評価される式) {
  // 処理
}

for (ループ開始時に実行される式; 条件式; 各繰り返しの後に評価される式) :
  // 処理
endfor;
```

# foreach
配列、オブジェクトをループで処理するときに使える便利な方法。
``` php
foreach (反復できる式 as $value) {
}

foreach (反復できる式 as $key => $value) {
}
```
