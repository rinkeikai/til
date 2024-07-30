# すぬけ君の操作回数問題

## 問題文

黒板に N 個の正の整数 A1,...,AN が書かれています。すぬけ君は、黒板に書かれている整数がすべて偶数であるとき、次の操作を行うことができます。

- 黒板に書かれている整数すべてを、2 で割ったものに置き換える。

すぬけ君は最大で何回操作を行うことができるかを求めてください。

### 制約
- 1 ≤ N ≤ 200
- 1 ≤ Ai ≤ 10^9

### 入力
入力は以下の形式で標準入力から与えられます。
```
N
A1 A2 ... AN
```


### 出力
すぬけ君は最大で何回操作を行うことができるかを出力してください。

## コード

以下に、問題を解決するJavaScriptのコードを示します。

```javascript
// inputに入力データ全体が入る
function Main(input) {
    
    // 入力データを行ごとに分割
    input = input.split("\n");

    // 最初の行は整数N (整数の数)
    var N = Number(input[0]);
    
    // 2行目以降はN個の整数
    var num = input[1].split(" ").map(Number);

    // 操作回数のカウンタ
    var cnt = 0;

    // 無限ループ
    for(;;){
        // 偶数でない整数があるかを示すフラグ
        var frg = false;

        // 各整数についてチェック
        for(var i = 0; i < N; i++){
            // 奇数が見つかったらフラグを立ててループを抜ける
            if (num[i] % 2 != 0){
                frg = true;
                break;
            }
            // 各整数を2で割る
            num[i] = num[i] / 2;
        }

        // 奇数が見つかった場合は操作を終了
        if(frg){
            break;
        }

        // 操作回数をカウント
        cnt++;
    }

    // 操作回数を出力
    console.log(cnt);
}

// ローカル入力文字列テンプレート
let input = `6
382253568 723152896 37802240 379425024 404894720 471526144`;

// 関数を実行
Main(input);
```
## フラグ部分の詳細説明
### 1.フラグの初期化:
```js
var frg = false;
```
・無限ループのたびにfrg（フラグ）をfalseに初期化します。  
・frgは奇数が見つかったかどうかを追跡するための変数です。奇数が見つかるとtrueに設定されます。  
### 2.整数のチェックと操作:
```js
for(var i = 0; i < N; i++){
    if (num[i] % 2 != 0){
        frg = true;
        break;
    }
    num[i] = num[i] / 2;
}
```
・各整数`num[i]`に対して、`num[i] % 2 != 0`（奇数であるか）をチェックします。  
・奇数が見つかった場合：
  -frgをtrueに設定します。  
  -break文により内側のforループを終了します。  
・奇数が見つからない場合：  
  -`num[i]`を2で割ります。この操作はすべての整数が偶数であると確認された後に行われます。
### 3.操作の終了条件:
```js
if(frg){
    break;
}
```
・内側の`for`ループが終了した後、`frg`が`true`であるかをチェックします。  
・`frg`が`true`である場合、無限ループを終了します。これは少なくとも1つの奇数が見つかったことを意味します。  
・`frg`が`false`である場合、すべての整数が偶数であったことを意味するため、操作回数カウンタ`cnt`をインクリメントし、もう一度ループを続けます。
## まとめ
このフラグの役割は、  
整数のリストに奇数が含まれているかどうかを検出し、含まれていればループを終了することです。  
これにより、すべての整数が偶数でなくなるまで、整数を2で割る操作を繰り返すことができます。