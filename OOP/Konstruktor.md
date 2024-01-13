Konstruktoren initialisieren ein Opbjekt

- [[Zugriffsmodifizierer]] meistens **public**
- Name eines Konstruktors muss identisch mit dem Name der [[Klasse]] sein
- Konstruktoren haben keinen [[Methode#Rückgabewerte|Rückgabewert]] 
- Wird immer mit dem Wort **new** aufgerufen
- Initialisiert die Instanzvariablen
- Ohne [[Parameter]] ist es ein **Default Konstruktor**
- Eine Klasse kann mehrere Konstruktoren haben 
	- Diese müssen zwingende unterschiedliche [[Methode#Signatur|Signaturen]] haben

## Beispiel Konstruktor Deklaration
```java
public Temperatur(final float temperaturCelcius)
{
	this.temperaturCelcius = temperaturCelcius;
}
```

## Beispiel Konstruktor Aufruf
```java
Temperatur temperatur1 = new Temperatur(20f)
```