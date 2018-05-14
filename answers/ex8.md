## 課題8 解答
```java
public class Contract extends User {

  int contractTerm;


  Contract(String id, String firstName, String lastName, int age, int contractTerm) {
    super(id, firstName, lastName, age);
    this.contractTerm = contractTerm;
  }

  public String getFullName() {
//    return this.lastName + " " + this.firstName + "(Contract)";
    return super.getFullName() + "(Contract)";
  }
}
```
