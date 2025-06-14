Das Strategy-Pattern ist ein Design-Pattern, welches zusammengehörige Algorithmen gruppieren kann. Mit der Anwendung können Conditional-Statements wie Bsp. [[Switch als Go-To]] umgangen werden. Dies führt zu einer erhöhten [[OOP/Kohäsion]] sowie einer loseren [[OOP/Kopplung]].

**Beispiel** 
Es wird ein `TaxCaluclator` benötigt, welcher die Steuern in einem spezifischen Land berechnet.

Dafür wird eine Strategie benötigt:
```java
public interface TaxCalulator{
	double calculateTax(double income);
}
```
Nun werden die verschiedenen Strategien implementiert:
```java
public class USTaxCalucator implements TaxCalculator {
	@Override
	public double calculateTax(double income) {
		...
	}
}

public class SwissTaxCalucator implements TaxCalculator {
	@Override
	public double calculateTax(double income) {
		...
	}
}

public class GermanTaxCalucator implements TaxCalculator {
	@Override
	public double calculateTax(double income) {
		...
	}
}
```
Am Schluss muss die richtige Strategie noch dem sogenannten `Context` aufgerufen werden
```java
public class TaxProgram {
	private final TaxCalculator taxCalculator;

	public TaxProgram(TaxCalculator taxCalculator) {
		this.taxCalculator = taxCalculator;
	}

	public double calculate(double income) {
		taxCalculator.calculate(income);
	}
}
```
