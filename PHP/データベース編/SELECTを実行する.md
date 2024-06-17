# PHPデータベース
## SELECTを実行する
前回作った`$pdo`に定義されている`query()`メソッドを使って`SQL`を発行してみましょう。  
今回`SELECT 5 + 3`という簡単な`SQL`を書いてみます。  
なお、`SQL`の中で`シングルクオート`を使っていくこともあるので、  
このレッスンでは`ダブルクオーテーションマーク`で表現することにします。
```PHP
<?php

$pdo = new PDO(
  'mysql:host=db;dbname=myapp;charset=utf8mb4',
  'dbuser',
  'dbpass'
);

$pdo->query("SELECT 5 + 3");
```
### $stmt変数で受ける
それから`query()`メソッドの結果は`PDOStatement`と呼ばれるオブジェクトで返ってくるので、  
分かりやすく`$stmt`といった変数で受けてあげます。
```PHP
<?php

$pdo = new PDO(
  'mysql:host=db;dbname=myapp;charset=utf8mb4',
  'dbuser',
  'dbpass'
);

$stmt = $pdo->query("SELECT 5 + 3"); // $stmt変数で受ける
```
### fetch()メソッドで配列を取得
それからこちらの`$stmt`は単なる結果が入ったオブジェクトなので、　　
分かりやすく配列で取得したかった場合、単一の結果なら`fetch()`というメソッドを使ってあげます。
`$result`という変数で受けてあげて、`$stmt->fetch()`と書いてあげます。
```PHP
<?php

$pdo = new PDO(
  'mysql:host=db;dbname=myapp;charset=utf8mb4',
  'dbuser',
  'dbpass'
);

$stmt = $pdo->query("SELECT 5 + 3");
$result = $stmt->fetch(); // $result変数でfetch()メソッドを使い、配列を取得
```
そうすると、結果が配列で取得できるので、そのまま var_dump() で表示してあげましょう。
```PHP
<?php

$pdo = new PDO(
  'mysql:host=db;dbname=myapp;charset=utf8mb4',
  'dbuser',
  'dbpass'
);

$stmt = $pdo->query("SELECT 5 + 3");
$result = $stmt->fetch(); // $result変数でfetch()メソッドを使い、配列を取得
var_dump($result);
```
出力
```
~ $ php main.php
array(2) {
  ["5 + 3"]=>
  string(1) "8"
  [0]=>
  string(1) "8"
}
```
デフォルトだとカラム名がついた結果とインデックス番号がついた結果を両方返してくれるのですが、  
ちゃんと`5 + 3`の結果である`8`が返ってきているのが分かります。  
なお、ここで*カラム名がついた結果だけ*を常に取得したい場合、  
`PDO`のオプションを指定してあげます。  
`PDO::ATTR_DEFAULT_FETCH_MODE`を`PDO::FETCH_ASSOC`にしてくださいとしてあげればOKです。
※オプションは`[]`で囲む
```PHP
<?php

$pdo = new PDO(
  'mysql:host=db;dbname=myapp;charset=utf8mb4',
  'dbuser',
  'dbpass',
  [
  'PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,' // PDO のオプションを指定する
  ]
);

$stmt = $pdo->query("SELECT 5 + 3");
$result = $stmt->fetch();
var_dump($result);
```
出力
```
~ $ php main.php
array(1) {
  ["5 + 3"]=>
  string(1) "8"
}
```
*カラム名がついた結果だけ*取得できている。
