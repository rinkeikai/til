# N行のデータの入力 JavaScript編
## 標準入力でN行それぞれで文字列が与えられるので、それらを入力して、順にそのままN行で出力してください。
### 入力される値　　
1行目でNが与えらます。続くN行の各行で文字列が与えられます。
入力値最終行の末尾に改行が１つ入ります。文字列は標準入力から渡されます。
###  期待される値
N行での出力

---
#### 入力例１
```
3
aaaaa
bbbbbb
cccc
```
#### 出力例1
```
aaaaa
bbbbbb
cccc
```
---

#### 入力例２
```
1
a b c
```
#### 出力例２
```
a b c
```
---

#### 入力例３
```
5
4
3
2
1
0
```
#### 出力例３
```
4
3
2
1
0
```
---

#### 入力例４
```
10
31415926
a b c d
3
4
5
6
7
8
9
ZZZZZZZZZ
```
#### 出力例４
```
31415926
a b c d
3
4
5
6
7
8
9
ZZZZZZZZZ
```
---

### 回答コード
```js
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
    var n = parseInt(lines[0]); //変数nに、１行目の値（N行）を取得（parseIntを使い整数値にする）
    for(var i = 1;i<=n;i++){
  console.log(lines[i]);}　//n回分（N行）出力する。初回インデックスiは入力値の２行目なので（i = 1）とする
});
```
