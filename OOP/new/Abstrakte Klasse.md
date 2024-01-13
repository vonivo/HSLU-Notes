- Können nicht instanziiert werden
- Definieren einen validen Typ
- Verfügen über keine *vollständige* Implementation
	- Teile können bereits implementiert werden (mix aus abstrakt und konkret)
- Abstrakte Methoden legen eine Schnittstelle fest und erzwingen das sie anderorts implementiert werden (Spezialisierung → [[Vererbung]])


Schlüsselwort: `abstract` 
- Möglich für [[Klasse|Klassen]] und [[Methode|Methoden]]

Unterscheidung: 
- Verfügt eine [[Klasse]] über mindestens eine Abstrakte [[Methode]] muss die [[Klasse]] ebenfalls abstrakt sein
- [[Klasse|Klassen]] welche nur über abstrakte [[Methode|Methoden]] verfügen sind **vollständig** abstrakte Klassen
	- Sind sehr ähnlich zu [[Interface|Interfaces]] → [[Interface|Intefaces]] sind meist die besser alternative

Naming:
Abstrakte Klassen sollten mit einem *Abstract* vor dem eigentlichen Namen als Abstract markiert werden 

## Best Practices
- **Abstrakte Klassen sollte eher zurückhaltend eingesetzt werden**
- Abstrakte Klassen sollte mindestens ein abstrakte Methoden enthalten
# Beispiele
## Vollständig Abstrakte [[Klasse]]

```java
public abstract class AbstractSwitch {

	public abstract void switchOn();
	
	public abstract void switchOff();
	
	public abstract boolean isSwitchedOn();
	
	public abstract boolean isSwitchedOff();
	
}
```

## Nicht vollständig Abstrakte [[Klasse]]

```java
public abstract class AbstractSwitch {
	private boolean switchedOn = false; 

	public abstract void switchOn();
	
	public abstract void switchOff();
	
	public boolean isSwitchedOn();
	{
		return this.switchedOn;
	}
	
	public boolean isSwitchedOff();
	{
		return !this.switchedOn;
	}
		
}
```