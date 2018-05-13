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
		show(userFirstName, userLastName, colleagueUserFirstName, colleagueUserLastName, colleagueUserAge, articleTitle,
				articleBody);
	}

	private static void show(String userFirstName, String userLastName, String colleagueUserFirstName,
			String colleagueUserLastName, int colleagueUserAge, String articleTitle, String articleBody) {
		System.out.println("Hello, " + getFullName(userLastName, userFirstName));
		System.out.println("Your colleague is " + getFullName(colleagueUserLastName, colleagueUserFirstName) + "Age:"
				+ colleagueUserAge);
		System.out.println();
		System.out.println("Title: " + articleTitle);
		System.out.println("Body: " + articleBody);
	}

	private static String getFullName(String lastName, String firstName) {
		return lastName + " " + firstName;
	}
}
```
FullNameの作成処理をメソッド化しました。
記述量が増えてむしろ大変になったと感じるでしょうか？

例えば、あなたに後輩ができて、画面にフルネームを出力してくださいと指示したとしましょう。
後輩は以下のように正確に記述してくれるでしょうか。
```
userFirstName + " " + userLastName
```
半角スペースが抜けてしまったり、全角スペースになってしまったり、
姓名を逆にしてしまったり、そんなミスが発生するかもしれません。
フルネームを出力する画面が数画面であれば、あなたがレビューして修正すればいいでしょう。
しかし、10も20も画面があったらどうなるでしょうか。
レビューだけで半日かかってしまいますし、見落とす可能性も高くなります。
何度も同じ事を書きそうであれば、メソッド化して再利用することを目指しましょう。
