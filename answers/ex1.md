## 課題1 解答  
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
    show(userFirstName, userLastName, colleagueUserFirstName, colleagueUserLastName, colleagueUserAge, articleTitle, articleBody);  
  }  

  private static void show(String userFirstName, String userLastName, String colleagueUserFirstName, String colleagueUserLastName, int colleagueUserAge, String articleTitle, String articleBody) {  
    System.out.println("Hello, " + userLastName + " " + userFirstName);  
    System.out.println("Your colleague is " + colleagueUserLastName + " " + colleagueUserFirstName + " Age:" + colleagueUserAge);  
    System.out.println();  
    System.out.println("Title: " + articleTitle);  
    System.out.println("Body: " + articleBody);  
  }  
}  
```  
