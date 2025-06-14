- Reine Schnittstelle
- Vollständig Abstrakt 
	- Keine Möglichkeit Objekte zu instanziieren 
- Definieren einen validen Typ
- Interfaces sind besonders nützlich da man Klassen als Interface [[Subtyping und Casting|casten]] kann und so über unterschiedliche Objekte die selbe Operation ausgeführt werden kann nur weil die alle dasselbe Interface implementieren ([[Polymorphie]])
- Interfaces können überall wo eine [[Klasse]] deklariert wird genutzt werden ([[Lokale Variable|Lokale Variablen]], [[Attribut|Attribute]], [[Parameter]], etc.)
- Interfaces tragen zu einer losen [[OOP/Kopplung]] bei
	
- Interfaces enthalten:
	- Ausschliesslich [[Methode#Methodenkopf|Methodenköpfe]]
	- Keine [[Attribut|Attribute]] 
	- Keine Implementation
	- *Theoretisch sind Attribute und Implementationen möglich **das ist aber nicht empfohlen**

- Interfaces beschreiben ausschließlich das öffentliche Verhalten (eine Rolle)
- Als funktionale Interfaces bezeichnet man Interfaces mit nur einer [[Methode]] ^ebc981

Schlüsselwort: `interface`
- Methoden eines Interfaces sind implizit `public` und `abstract` diese [[OOP/Schlüsselwörter]] können entfallen

- **Interfaces werden von [[Klasse|Klassen]] implementiert**
	- Die [[Klasse]] eignet sich somit die Rolle an
	- Es können auch mehrere Interfaces von eine [[Klasse]] implementiert werden (diese werden per *Komma* getrennt)
	- Eine [[Klasse]] muss **alle** Methoden des Interfaces implementieren
	
- **Schnittstellen sollten immer mit [[JavaDoc]] dokumentiert werden**
- **Lieber ein Interface zu viel als eines zu wenig**

## Naming
Variante 1: 
- “able” - Postfix anhängen (Switch*able*, Count*able*)

Variante 2: 
- “Interface” - Postfix anhängen (Print*Interface*, Event*Interface*)
## Beispiele
### Interface
```java
public interface Switchable {
	void switchOn();

	void switchOff();
}
```

### Interface Implementation
```java
public class Lampe implements Switchable {
	private int lumen; 
	private static final int MAX_LUMEN = 800;
	
	@Override 
	public void switchOn() {
		if (this.isSwitchedOff()){
			this.lumen = MAX_LUMEN;
		}
	}
	
	@Override 
	public void switchOff() {
		if (this.isSwitchedOff()){
			this.lumen = 0;
		}
	}

}
```