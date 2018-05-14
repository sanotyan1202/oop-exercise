## 課題6 解答
```java
public class User {
  String id;
  String firstName;
  String lastName;
  int age;

  User(String id, String firstName, String lastName, int age) {
    this.id = id;
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
  }

  public String getFullName() {
    return this.lastName + " " + this.firstName;
  }
}
```

```java
public class Article {
  String title;
  String body;

  Article(String title, String body) {
    this.title = title;
    this.body = body;
  }
}
```
