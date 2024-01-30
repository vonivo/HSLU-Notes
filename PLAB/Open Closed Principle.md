Software sollte offen (open) für Erweiterungen sein, aber geschlossen für (closed) für Modifikationen.

Das heisst, es sollte möglich sein, neue Features zu bestehenden Code hinzuzufügen ohne grosse Änderungen vornehmen zu müssen.

## Beispiel
**ohne Open-Closed-Principle**
```java
public class Employee {
	private String name;
	private String role;

	public Employee(String name, String role) {...}

	public void performDuties() {
		if (role.equals("Developer")) {
			System.out.println(name + " is coding.");
		} else if (role.equals("Manager")) {
			System.out.println(name + " is managing.");
		} else if (role.equals("Tester")) {
			System.out.println(name + " is testing.");
		}
	}
}
```
Wenn bei diesem Beispiel nun eine neue Rolle hinzugefügt wird, muss nun immer die [[Methode]] `performDuties` angepasst werden.

**Mit Open-Closed Principle**
```java
public interface IEmployee {
	void performDuties();
}

public class Developer implements IEmployee {
	private String name;

	public Tester(String name) {...}

	@Override
	public void performDuties() {
		System.out.println(name + " is coding.");
	}
}

public class Manager implements IEmployee {
	private String name;

	public Tester(String name) {...}

	@Override
	public void performDuties() {
		System.out.println(name + " is managing.");
	}
}

public class Tester implements IEmployee {
	private String name;

	public Tester(String name) {...}

	@Override
	public void performDuties() {
		System.out.println(name + " is testing.");
	}
}
```
Bei diesem Beispiel mit einem [[Interface]] kann nun einfach eine neue [[Klasse]] als Rolle hinzugefügt werden und der bestehende Code muss nicht verändert werden.