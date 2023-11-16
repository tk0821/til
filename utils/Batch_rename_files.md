# ファイル名の一括変更

p_psから始まるgifファイルのファイル名のp_psをB_に変更する

```
 Get-ChildItem *.gif | Rename-Item -NewName {$_.Name -Replace 'p_ps(.*)', 'B_$1'}
```

`Get-ChileItem`でgifファイルのリストを取得し、それらを`Rename-Item`で変更している。

`-NewName {}`のブロック内はスクリプトブロックで、これを実行した値がNewNameとなる

`$_`はパイプに渡された変数。今回はChildItemのNameパラメータを使用。それを正規表現で置換する。
```
PS C:\Users\t_kan\Desktop\pinzu_all\pinzu_all> Get-ChildItem *.gif

    Directory: C:\Users\t_kan\Desktop\pinzu_all\pinzu_all

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---          2023/11/15    11:13           1071 B_1_0.gif
-a---          2023/11/15    11:13            597 B_1_1.gif
-a---          2023/11/15    11:13            597 B_1_2.gif
...
-a---          2023/11/15    11:13            833 B_9_5.gif
-a---          2023/11/15    11:13            933 B_9_6.gif
-a---          2023/11/15    11:13            940 B_9_7.gif
```
