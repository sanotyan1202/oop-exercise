## 課題7 解答
```java
public class Regular extends User {

  String deptName;

  Regular(String id, String firstName, String lastName, int age, String deptName) {
    super(id, firstName, lastName, age);
    this.deptName = deptName;
  }
}
```
```java
public class Contract extends User {

  int contractTerm;

  Contract(String id, String firstName, String lastName, int age, int contractTerm) {
    super(id, firstName, lastName, age);
    this.contractTerm = contractTerm;
  }
}
```

```java
class Main {
  public static void main(String[] args) {

    // ログインユーザー情報
    User user = new Regular("0001", "Taro", "Hoge", 20, "Engineering");

    // 同僚ユーザー情報
    User colleague = new Contract("0002", "Jiro", "Fuga", 22, 2);

    // 記事情報
    Article article = new Article("Hello", "World");

    // showメソッド呼び出し
    show(user, colleague, article);
  }

  private static void show(User user, User colleague, Article article) {
    System.out.println("Hello, " + user.getFullName());
    System.out.println("Your colleague is " + colleague.getFullName() + "Age:" + colleague.age);
    System.out.println();
    System.out.println("Title: " + article.title);
    System.out.println("Body: " + article.body);
  }
}
```
