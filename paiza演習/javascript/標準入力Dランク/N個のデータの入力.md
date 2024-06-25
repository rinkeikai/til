# 「N個のデータの入力 JavaScript編」
## 標準入力でN個の文字列が1行で与えられるので、それらを入力して、順にそのままN行で出力してください。
### 1行目でNが与えられます。2行目でN個の文字列が半角スペース区切りで与えれます。

入力例１
```
3
aaaaa bbbbbb cccc
```
出力例1
```
aaaaa
bbbbbb
cccc
```
入力例2
```
1
abc
```
出力例2
```
abc
```

入力例３
```
5
3 1 4 1 5
```
出力例３
```
3
1
4
1
5
```
入力例４
```
10
31415926 qqqqqq abab313 xyz31131 5 6 7 8 9 10
```
出力例４
```
31415926
qqqqqq
abab313
xyz31131
5
6
7
8
9
10
```

### 回答コード

```js script
process.stdin.resume();
process.stdin.setEncoding('utf8');
// 自分の得意な言語で
// Let's チャレンジ！！
var lines = [];
var reader = require('readline').createInterface({
  input: process.stdin,
  output: process.stdout
});
reader.on('line', (line) => {
  lines.push(line);
});
reader.on('close', () => {
    var n = parseInt(lines[0]); //n変数に１行目の値（N行）を取得
    var value = lines[1].split(' '); //２行目の値をvalue変数に取得（splitを使い' 'スペースを取り除く）
    for(var i = 0; i<n; i++){
  console.log(value[i]); //for文使い２行目で取得した値を（value変数）、n回分だけ出力
    }
});
```
