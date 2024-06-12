# PHP基本文法
## fgetsでユーザーからの入力を受け取る
### 文字列の操作１
インタラクティブに動作が試せるように、ユーザーから入力を受け取る方法を行う。  
`fgets`、`()`丸括弧、大文字で`STDIN`とすると、ユーザーに文字列を入力してもらって変数で受け取ることができる。  
※`fgets`→ファイルポインタから 1 行取得する
なお、この`STDIN`は「STanDard INput」つまり標準入力の略で、通常はターミナルからの入力を意味します。  
では、結果を変数に代入することができるので、  
今回は名前を入力してもらうことを想定しているので、"$name"という変数で受け取ることにします。
```PHP
<?php
  $name = fgets(STDIN);
```
`echo`を使い、変数を表示する。
```PHP
<?php
  $name = fgets(STDIN);
  echo $name . PHP_EOL;
```
ターミナル
```
~ $ php main.php
◼︎//ここに入力する。
```
出力
```
~ $ php main.php
Taro //入力した文字列
Taro //表示された文字列

```
ここで入力してもらうときに、入力を促すためのメッセージを表示させために、  
`fgets`の前に`echo`で、「Your name?」として見やすいように、最後に半角空白を入れます。
なお、ここで最後に`PHP_EOL`を付けないので、この「Your name?」半角スペースのあとで入力ができるようになる。
```PHP
<?php
  echo Your name? ; //?の後に半角スペース
  $name = fgets(STDIN);
  echo $name . PHP_EOL;
```
ターミナル
```
~ $ php main.php
Your name? ◼︎//ここに入力する。
```
出力
```
~ $ php main.php
Your name? Taro //入力した文字列
Taro //表示された文字列

```
