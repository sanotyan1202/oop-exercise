## 課題4 解答
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
    System.out.println("Hello, " + getFullName(user.lastName, user.firstName));
    System.out.println("Your colleague is " + getFullName(colleague.lastName, colleague.firstName) + "Age:" + colleague.age);
    System.out.println();
    System.out.println("Title: " + article.title);
    System.out.println("Body: " + article.body);
  }

  private static String getFullName(String lastName, String firstName) {
    return lastName + " " + firstName;
  }
}
```
