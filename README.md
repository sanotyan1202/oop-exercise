# オブジェクト指向復習課題


## 課題1 - メソッドの定義  
社内SNSのようなアプリを作りたいとしましょう。  
以下のような情報を扱うとします。  

#### ログインユーザー情報  
- ユーザーID  
- 姓  
- 名  
- 年齢  

#### 同僚ユーザー情報  
- ユーザーID  
- 姓  
- 名  
- 年齢  

#### 記事情報  
- タイトル  
- 記事内容  

#### [問] exerciseプロジェクトを作成してください。  
#### [問] 画面に以下のように出力するshowメソッドを定義してください。  

```  
Hello, Hoge Taro  
Your colleague is Fuga JiroAge:22  

Title:  Hello  
Body: World  
```  

```java  
class Main {  
	public static void main(String[] args) {  

		// ログインユーザー情報  
		String userId = "0001";  
		String userLastName = "Taro";  
		String userFirstName = "Hoge";  
		int userAge = 20;  

		// 同僚ユーザー情報  
		String colleagueUserId = "0002";  
		String colleagueUserLastName = "Jiro";  
		String colleagueUserFirstName = "Fuga";  
		int colleagueUserAge = 22;  

		// 記事情報  
		String articleTitle = " Hello";  
		String articleBody = "World";  

		// showメソッド呼び出し  
		show(???);
	}  

	private static ??? show(???) {  
		System.out.println("Hello, " ???);  
		System.out.println("Your colleague is " ???);  
		System.out.println();  
		System.out.println("Title: " ???);  
		System.out.println("Body: " ???);  
	}  
}  
```  

## 課題2 - メソッド定義  

フルネームを画面に出力するために、毎回以下のようにコーディングしていては効率が悪く、ミスの原因にもなります。  
```  
userFirstName + " " + userLastName  
```  
フルネームは今後、別の画面でも使う事が予想されるのでメソッド化したいと考えます。  

#### [問] getFullNameメソッドを定義してください。  

```java  
class Main {  
	public static void main(String[] args) {  

		// ログインユーザー情報  
		String userId = "0001";  
    String userFirstName = "Taro";  
		String userLastName = "Hoge";  
		int userAge = 20;  

		// 同僚ユーザー情報  
		String colleagueUserId = "0002";  
    String colleagueUserFirstName = "Jiro";  
		String colleagueUserLastName = "Fuga";  
		int colleagueUserAge = 22;  

		// 記事情報  
		String articleTitle = " Hello";  
		String articleBody = "World";  

		// showメソッド呼び出し  
		show(userFirstName, userLastName, colleagueUserFirstName,
		     colleagueUserLastName, colleagueUserAge, articleTitle, articleBody);  
	}  

	private static void show(String userFirstName, String userLastName,
	                         String colleagueUserFirstName, String colleagueUserLastName,
													 int colleagueUserAge, String articleTitle, String articleBody) {  
		System.out.println("Hello, " + ???);  
		System.out.println("Your colleague is " + ??? + " Age:" + colleagueUserAge);  
		System.out.println();  
		System.out.println("Title: " + articleTitle);  
		System.out.println("Body: " + articleBody);  
	}  

	private static ??? getFullName(???) {  
    ???  
	}  
}  
 ```  
 > 「???」を埋めてください。  

## 課題3 クラス定義  
ところで、showメソッドの引数が多すぎて読みづらいなと思いませんでしたか？  
showメソッドを呼び出した時、順番通り間違えずに値を渡すことができたでしょうか？  
ユーザーの情報はまとめてユーザーという変数に、  
記事の情報はまとめて記事という変数に、  
代入できたらスッキリしそうですよね。  
クラスを作成することで情報をまとめて扱う事ができます。  

#### [問] ユーザー情報をまとめるUserクラスを定義してください  
#### [問] 記事情報をまとめるArticleクラスを定義してください  

```java  
class User {  
  ???  
  ???  
  ???  
  ???  
}  
```  
```java  
class Article {  
  ???  
  ???  
}  
```  

## 課題4 インスタンス生成  
Userクラスを定義したので、ユーザー情報をまとめて扱えるようになりました。  
次は、ユーザー情報自体を作らなくてはなりません。  
Javaでは、整数なら「1」と打てば、1という整数情報が作成されます。  
文字列なら「"Hello"」と打てば、文字列情報が作成されます。  
自分で作成したクラスなら「new クラス名()」と打つ必要があります。  

#### [問] Userクラス、Articleクラスのインスタンスを生成してください  
#### [問] showメソッドの引数を、Userクラス、Articleインスタンスを受け取るように変更してください  

```java  
lass Main {  
	public static void main(String[] args) {  

		// ログインユーザー情報  
		??? user = ???  
		user.id = "0001";  
		user.firstName = "Taro";  
		user.lastName = "Hoge";  
		user.age = 20;  

		// 同僚ユーザー情報  
		??? colleague = ???;  
		colleague.id = "0002";  
		colleague.firstName = "Jiro";  
		colleague.lastName = "Fuga";  
		colleague.age = 22;  

		// 記事情報  
		??? article = ???  
		article.title = " Hello";  
		article.body = "World";  

		// showメソッド呼び出し  
		show(???);  
	}  

	private static void show(???) {  
		System.out.println("Hello, " + getFullName(???));  
		System.out.println("Your colleague is " + getFullName(???) + " Age:" + ???);  
		System.out.println();  
		System.out.println("Title: " + ???);  
		System.out.println("Body: " + ???);  
	}  

	private static String getFullName(String lastName, String firstName) {  
		return lastName + " " + firstName;  
	}  
}  
```  

## 課題5 メソッド定義  
Userクラスにユーザー情報を全てまとめる事ができるようになりました。  
getFullNameメソッドに違和感を覚えないでしょうか？  
getFullNameメソッドはユーザー情報に関するメソッドなので、Userクラスに定義すべきです。  

#### [問] getFullNameメソッドをUserクラスに定義してください。  

```java  
public class User {  
	String id;  
	String firstName;  
	String lastName;  
	int age;  

  public String getFullName() {  
    ???  
  }  
}  
```  
#### [問] MainクラスからgetFullNameメソッドを削除してください  
#### [問] UserクラスのgetFullNameメソッドを呼び出してください  
```java  
class Main {  
	public static void main(String[] args) {  

		// ログインユーザー情報  
		User user = new User();  
		user.id = "0001";  
		user.firstName = "Taro";  
		user.lastName = "Hoge";  
		user.age = 20;  

		// 同僚ユーザー情報  
		User colleague = new User();  
		colleague.id = "0002";  
		colleague.firstName = "Jiro";  
		colleague.lastName = "Fuga";  
		colleague.age = 22;  

		// 記事情報  
		Article article = new Article();  
		article.title = " Hello";  
		article.body = "World";  

		// showメソッド呼び出し  
		show(user, colleague, article);  
	}  

	private static void show(User user, User colleague, Article article) {  
		System.out.println("Hello, " + ???);  
		System.out.println("Your colleague is " + ??? + " Age:" + colleague.age);  
		System.out.println();  
		System.out.println("Title: " + article.title);  
		System.out.println("Body: " + article.body);  
	}  
}  
```  

## 課題6 コンストラクタ定義  
Javaの配列を思い出してください。  
```  
int[] ary = new int[3];  
ary[0] = 82;  
ary[1] = 96;  
ary[2] = 77;  
```  
とする方法と、  
```  
int[] ary = {82, 96, 77};  
```  
とする方法がありました。  
おそらく大半の人は後者の使い方がスマートだと感じたはずです。  
コンストラクタを用いる事で、ユーザー情報をスマートに作成することができます。  

#### [問] Userクラスの全てのフィールドを設定するコンストラクタを作成してください  
#### [問] Articleクラスの全てのフィールドを設定するコンストラクタを作成してください  

```java  
public class User {  
	String id;  
	String firstName;  
	String lastName;  
	int age;  

	???  

	public String getFullName() {  
		return this.lastName + " " + this.firstName;  
	}  
}  
```  

```java  
public class Article {  
	String title;  
	String body;  

  ???  
}  
```  

コンストラクタを独自に定義することで、デフォルトコンストラクタが自動的に作成されなくなります。  
これは空のインスンタンスを作成されるのを防ぐためです。  
これにより、インスタンスに値を代入し忘れる等のミスを減らすことができます。  
既存のmainメソッドではデフォルトコンストラクタを使用していたのでコンパイルエラーが表示されているはずです。  

#### [問] mainメソッドのコンパイルエラーを修正してください  

```  
ノーヒント  
```  


## 課題7 継承  
ユーザー情報を正社員と契約社員に分けることになりました。  
正社員には所属部署が、契約社員には契約期間の情報が必要となったためです。  
全く新しくクラスを定義してもいいですが、せっかくなのでUserクラスを再利用しましょう。  

#### [問] Userクラスを継承してRegularクラス（正社員）を作成してください  
#### [問] Userクラスを継承してContractクラス（契約社員）を作成してください  

```java  
public class Regular ??? {  

	String deptName;  

  // コンストラクタ  
  ???  
}  
```  

```java  
public class Contract  ??? {  

	int contractTerm;  

  // コンストラクタ  
  ???  
}  
```  

#### [問] ログインユーザー情報を正社員のインスタンスに変更してください（部署名は"Engineering"とします）  
#### [問] 同僚ユーザー情報を契約社員のインスタンスに変更してください（契約期間は2ヶ月とします）  

```java  
class Main {  
	public static void main(String[] args) {  

		// ログインユーザー情報  
		User user = ???  

		// 同僚ユーザー情報  
		User colleague = ???  

		// 記事情報  
		Article article = new Article("Hello", "World");  

		// showメソッド呼び出し  
		show(user, colleague, article);  
	}  

	private static void show(User user, User colleague, Article article) {  
		System.out.println("Hello, " + user.getFullName());  
		System.out.println("Your colleague is " + colleague.getFullName() + " Age:" + colleague.age);  
		System.out.println();  
		System.out.println("Title: " + article.title);  
		System.out.println("Body: " + article.body);  
	}  
}  
```  
クラスを継承することで、メソッドやフィールドを引き継ぐことができます。

## 課題8 オーバーライド  
フルネームを画面に表示する時、契約社員の時は「(Contract)」と後ろに表示することになりました。  
どうやって実装すべきでしょうか？if文を使って契約社員だったら「(Contract)」と出力しますか？  
一度書いてみようとしてください。結構難しい上に、読みづらい処理になってしまうと思います。  
Javaには継承先のクラスで処理を書き換える仕組みがありました。  
オーバーライドです。  

#### [問] ContractクラスのgetFullNameメソッドをオーバーライドしてフルネームの後ろに(Contract)と出力されるようにしてください。  

```  
ノーヒント  
```  

出力結果  
```  
Hello, Hoge Taro  
Your colleague is Fuga Jiro(Contract) Age:22  

Title: Hello  
Body: World  
```  

## 課題9 ポリモフィズム  
同僚がContractクラスのインスタンスになったにも関わらず、showメソッドの処理を変更する必要はありませんでした。  
それなのに出力結果には「(Contract)」が追加されています。  
このように同じ型の変数の同じメソッドを呼んでいるのに、代入されているインスタンスの型によって実際の処理が異なることをポリモフィズムと言います。  
ポリモフィズムは同じ機能を持つ異なるクラスが追加する時にも活きてきます。  

#### [問] Userクラスを継承したPartTimerクラスを追加してください（特に新しい情報は必要ありません）  
#### [問] PartTimerのフルネームの後ろには「(PartTime)」と出力されるようにしてください  
#### [問] 同僚のクラスをPartTimerクラスに変更してください  

```  
ノーヒント  
```  

## 課題10 抽象クラス  
これで、このシステムを扱えるユーザーは正社員、契約社員、パートタイマーとなりました。  
すると、Userクラスのインスタンスに違和感を覚えないでしょうか。  
Userというユーザーは実在せず、あくまでUserは概念です。  
Userクラスのインスタンスを生成することは、それ自体が間違いです。  
間違いを減らすためにも、Userクラスのインスタンスは作成できないようにしましょう。  

#### [問] Userクラスを抽象クラスに変更してください  

```  
ノーヒント  
```  
