
```java
public class PartTimer extends User {

	PartTimer(String id, String firstName, String lastName, int age) {
		super(id, firstName, lastName, age);
	}

	public String getFullName() {
		return super.getFullName() + "(PartTime)";
	}
}
```
