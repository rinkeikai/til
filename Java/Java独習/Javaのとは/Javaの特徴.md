# Javaとは？
## Javaの特徴
### オブジェクト指向
***オブジェクト指向*** とは、プログラムの中で扱い対象をモノ（オブジェクト）になぞらえ、  
オブジェクトの組み合わせによってアプリを形成していく手法のことである。  
例えば、一般的なアプリであれば、文字列を入力するためのテキストボックスがあり、操作を選択するためのメニューバーがあり、  
また、何かしら動作を確定するためのボタンがあります。  
これら全て***オブジェクト***です。  
また、アプリからファイル/ネットワークなどを経由して情報を取得することもあるが、  
こうした機能を提供するのもオブジェクトであり、オブジェクトによって受け渡されるデータもまた、オブジェクトです。
### Java仮想マシン
Javaは、***Java仮想マシン***と呼ばれるソフトウェアの上で動作する。  
旧来の、たとえばC／C＋＋のような言語は、プログラマーによって書かれたコードを、  
それぞれのプラットフォームが理解できる言語ーーマシン語に変換してから実行していました。  
この変換のことを***コンパイル***と言います。  
マシン語はそれぞれプラットフォーム固有のものなので、例えばWindows環境に対応したアプリをLinux、macOSなど他の環境で実行することはできません。  
Javaも同じく、コードを実行するためにコンパイルという手順を経ますが、その出力はマシン語ではなく、  
***Javaバイトコード***と呼ばれる、Java仮想マシンが解釈できる形式となります。  
このバイトコードを、それぞれのプラットフォームに対応した仮想マシンが**ネイティブコード**に変換した上で実行するのです。  
  よってJavaでは**個々のプラットフォームに応じて実行ファイルを準備する必要がない。**
### ガベージコレクション
***ガベージコレクション***（GC）とは、プログラムが確保したメモリ領域のうち、利用されなくなったものを自動的に解放する機能のことです。  
古いプログラミング言語では、メモリの確保から解放まで全て自身で管理しなければならず、  
解放のし忘れはそのまま**メモリリーク**などの致命的なバグの原因にもなっていました。  
***メモリリーク***とは、解放されないメモリ領域がアプリを利用し続けることで徐々に増えていき、メモリが逼迫する状況のことです。  
逆に、メモリの解放を重複して行うことで、アプリの挙動が不安定になる場合もある。  
しかし、ガベージコレクションによって、メモリの解放を明示的に記述する必要がなくなるので、これらの問題は自ずと解決します。  
またメモリ管理というアプリ本来の目的からすれば本質的でないコーディングから解放されることで、  
**コードがよりコンパクトに表せ**、見通しも良くなるというメリットもあります。
