Exceptionhandling bezeichnet die Fehlerbehandlung

**Grundsatz: Fehler so nahe an der Quelle wie möglich, und so weit davon entfernt wie nötig behandeln!**

Folgende Fragen sind wichtig:
- Wie ist es zu behandeln?
- Auf welcher Ebene soll er behandelt werden?
- Ist die Delegation an eine höhere Ebene sinnvoll?
- Macht eine Nachfrage bei dem Benutzenden Sinn
- Muss die Verarbeitung / das Programm abgebrochen werden?

**Wann immer möglich sollten vorhandene Typen von Exceptions verwendet werden**

## Best Practices
- Verschachtelung und Rethrowing von Exceptions sparsam einsetzen
- Exceptions dokumentieren
- Exceptions nie für die normale Steuerung eines Programms verwenden (Ressourcen intensiv)
- So wenig eigene Exceptiontypen wie möglich verwenden 
- Keine leeren catch Blöcke verwenden
- [[OOP/Logging]] um Fehler festzuhalten
- Fehlerbehandlung testen [[Exceptiontesting]]
# Prinzip
Auslösen: 
In einem Fehlerfall werden Exceptions erzeugt (`new`) und dann geworfen (`throw`)
`throw` → löst eine Exception aus
`throws` → Reicht eine Exception an die höhere Aufrufebene weiter 

Behandeln:
Exception werden auf der nächst höheren Ebene gefangen (`catch`) oder weitergereicht (`throws`)
`try` → Markiert einen Block in welchem Exceptions erwartet werden
`catch` → Markiert einen Block für die Behandlung der gefangenen Exceptions
`finally` → Markiert einen optionalen Block der immer ausgeführt wird

## Arten von Fehlern
**Error** → Nicht behebbar, wird meist nicht behandelt
**Runtime Exception** → Behebbare, wenig erwartete Fehler
- Behebung diese Fehler ist optional (unchecked Exception)
**Exception** → Behebbare, erwartete Fehler
- Behebung dieser Fehler ist zwingend (checked Exception)

Eigene Exceptions werden von RuntimeException oder Exception [[Vererbung|spezialisiert]]. 


## Exceptions auslösen (Quelle)
Wird eine Exception ausgelöst wird die [[Methode]] sofort abgebrochen

Exception werden geworfen für einen Fehler welcher nicht an Ort und Stelle behandelt werden kann

Checked Exceptions brauchen eine `throws` Deklaration im Methodenkopf

**Exceptions sollte nie direkt dort behandelt werden wo sie geworfen wurden**

### Beispiele
Checked Exception
```java
public void setTemperatureCelcius(float celcius) throws IllegalArgumentException
{
	if (temperatur > -273.15){
		this.temperatureCelcius = celcius; 
	}
	else
	{
		throw new IllegalArgumentException("Not a valid measurement of temperature"); 
	}
}
```
Unchecked Exception
```java
public void setTemperatureCelcius(float celcius)
{
	if (temperatur > -273.15){
		this.temperatureCelcius = celcius; 
	}
	else
	{
		throw new IllegalArgumentException("Not a valid measurement of temperature"); 
	}
}
```

## Exceptions Behandeln
- Die Behandlung einer Exception findet of in einer anderen [[Klasse]] statt als deren Auslösung
- Es gibt nur einen try Block 
- Es kann mehrere catch Blöcke geben
	- Es wird immer nur der erste zutreffende Block ausgeführt
	- catch Blöcken müssen nach Typ sortiert werden
		- Spezialisierte Exceptions **vor** den generalisierten Exceptions
- Existiert mindestens ein catch Block ist der finally Block optional
### Beispiel 
```java
try {
	Temperatur temperatur = new Temperatur(value, TemperatureMeasurement.CELCIUS);
    LOG.info("Eingegebene Temperatur: " + temperatur.getTemperaturCelcius() + " Celcius");  
    
    } catch (IllegalArgumentException iae) {   
	    LOG.error("Es wurde keine gültige Temperatur verwendet " + iae.toString());
    }
```

#### Multiple Catch
Ein Multiple Catch kann verwendet werden wenn amn mehrere Exceptions erwartet welche man auf die selbe Art behandelt. Diese werden durch ein pipe Symbol getrennt. 
```java
try {
	Temperatur temperatur = new Temperatur(value, TemperatureMeasurement.CELCIUS);
    LOG.info("Eingegebene Temperatur: " + temperatur.getTemperaturCelcius() + " Celcius");  
    
    } catch (IllegalArgumentException | NumberFormatException ex) {   
	    LOG.error("Es wurde keine gültige Temperatur verwendet " + ex.toString());
    }
```


## Exceptions weiterleiten
- Unchecked Exception werden automatisch weitergeleitet wenn sie nicht behandelt werden
- Checked Exceptions müssen explizit weitergeleitet werden

# Testing
Siehe [[Exceptiontesting]]