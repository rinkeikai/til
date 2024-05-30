# クラスを定義する  
## User データ型を定義するには...
クラスを定義するには、  
プログラム本体の前で定義する必要がある。
```Java
//ココに定義！！//

public class MyApp {
public static void main(String[] args) {
  }
}
```
**『class』** というキーワードを使って、
データ型の名前<sub>（今回はUser）</sub> 、 { }<sub>（ブロック）</sub>とする。  
なお、classで作る独自のデータ型の名前は、 **『大文字』** から始める必要がある。
```Java
class User {

}

public class MyApp {
public static void main(String[] args) {
  }
}
```
このUserクラスのデータ構造を定義したいので、  
**保持したい『値』を『変数』のように宣言する。**  
今回は、名前と点数を管理したいので、それぞれ文字列型（String）と整数型（int）で宣言する。  
なお、class内で定義する変数のことを、このクラスの **field** と呼びます。
```Java
class User {
  String name; //field
  int score; //field
}

public class MyApp {
public static void main(String[] args) {
  }
}
```
Userクラスの定義ができたので、このUser型の値、インスタンスを作ってみます。  
**『new』** というキーワードを使って、データ型の名前、( ) とする。  
```Java
class User {
  String name; //field
  int score; //field
}

public class MyApp {
public static void main(String[] args) {
  new User() //１つの値になる。
  }
}
```
これで1つの値になるので、変数に代入することができる。  
いくつか値を作っていきたいので、とりあえず「user1」に代入していく。  
また、変数を宣言するには、データ型を書く必要があるので、  
「user1」の前に『User型』とする
```Java
class User {
  String name; //field
  int score; //field
}

public class MyApp {
public static void main(String[] args) {
  User user1 = new User();
  }
}
```
さらに、「user2」も作っていく。
```Java
class User {
  String name; //field
  int score; //field
}

public class MyApp {
public static void main(String[] args) {
  User user1 = new User();
  User user2 = new User();
  }
}
```
