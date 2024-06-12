# PHP基本文法
##  var_dump､trimを使ってみよう
`fgets(STDIN)`を使った表示の際の、  
最後の空行が「どこからきて」「どのように取り除くか」を行う。
まずは`var_dump`という命令分を使って、値の詳細を調べる。
```PHP
<?php
  echo "Your name? ";
$name = fgets(STDIN);
var_dump($name);
//echo $name . PHP_EOL;
```
出力
```
~ $ php main.php
Your name? Taro
string(5) "Taro
"
```
`string(5)`というのは文字列が「５」あるという意味であり、  
`Taro`という値の最後に改行が入っていますが、  
これは`fgets`で入力するときにエンターキーを押しているので、その分も文字列に含まれてしまっている。  
この最後の改行も 「1」 文字分なので、`Taro`の 「4」 文字と合わせて、文字数が 「5」 文字になっている、という点にも注意しておく。  
では、この最後の改行を`trim`という命令を使い取り除いていく。
どうするかというと、`fgets`で受け取る値を、直接`trim()`で囲ってしまえば OK です。
```PHP
<?php
  echo "Your name? ";
$name = trim(fgets(STDIN));
//var_dump($name);
echo $name . PHP_EOL;
```
出力
```
~ $ php main.php
Your name? Taro
Taro
```
ユーザーから文字列を入力してもらうときには、この`trim`をよく使うので、使い方に慣れておくと良い。
