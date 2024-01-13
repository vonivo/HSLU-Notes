## Aufbau einer Klasse
### Reihenfolge
1. [[Attribut]]
2. [[Konstruktor]]
3. [[Methode]]

### Beispiel
```java
//Package Deklaration
package ch.hslu.oop.sw012;

/**
* Javadoc der Temperaturklasse
*/

public final class Temperatur { //Klassenrahmen
	// Klassenrumpf START
	// Attribute
	public float temperaturCelcius;

	// Konstruktoren
	public Temperatur(float temperaturCelcius)
	{
		this.temperaturCelcius = temperaturCelcius;
	}

	// Methoden
	public float getTemperaturCelcius()
	{
		return this.temperaturCelcius
	}
	// Klassenrumpf END
}
```

### Package und Name
- Beispiel: `ch.hslu.oop.sw07.person`
- Der umgekehrte Domainname (hslu.ch → ch.hslu)
- Pfadangabe ``\ch\hslu\oop\sw07\person.java``

