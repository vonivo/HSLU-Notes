- Verkörpert Verhalten eines Objektes
- Ermöglich Kommunikation und Interaktion zwischen Objekten
- Aufbau:  *[[Zugriffsmodifizierer]] Rückgabewert Name([[Datentyp]] Parametername){ ……..}*
	- Beispiel: 
		```java
			public void setTemperaturCelcius(float temperaturCelcius)
			{
				this.temperaturCelcius = temperaturCelcius;
			}
		```
	- [[Zugriffsmodifizierer]] public oder private
## Methodenkopf
Der Methodenkopf spezifiziert gewisse Rahmenbedingungen der Methode, wie den [[Zugriffsmodifizierer]] (private, public, package), den [[Datentyp]] des Rückgabewerts und die formalen [[Parameter]].


### [[Parameter]]
 - Eine Methode kann [[Parameter]] oder keine [[Parameter]] haben. 
 - Jeder [[Parameter]] bekommt einn [[Datentyp]]
 - [[Parameter]] sind nur innerhalb der Methode sichtbar
### Signatur
- Signatur einer Methodes → `Name(Datentyp Parametername)`
	- Innerhalb einer [[Klasse]] müssen alle Methoden ein andere Signatur haben
	- Beispiel `setTemperaturCelcius(float temperaturCelcius)`

### Rückgabewerte
- Der Rückgabewert besitzt immer ein [[Datentyp]]
- Wird per **return** im Methodenrumpf zürckgegeben
-  Mit **return** wird die Ausführung einer Methode beendet
- Wenn es keinen Rückgabewert gibt wird die als [[Datentyp]] des Rückgabewert **void** verwendet
	- Bei **void** Methoden ist das **return** optional
- Wenn der [[Datentyp]] irgendetwas anderes als **void** ist dann braucht es zwingend ein **return**
- **return** funktioniert auch mit Ausdrücken und [[Selektion#Bedingung|Bedingungen]]
	- `return (a + 7);` → wenn `a = 2` gibt die Methoden `9` zurück
	- `return (a > 7);` → wenn `a = 2` gibt die Methoden `false` zurück
- Eine Methode kann nur einen Wert zurückliefern
## Methodenrumpf
Der Methodenrumpf enthält die eigentlichen Implementation der Methode
- Beinhaltet Deklarationen und Anweisungen
- Anweisungen un Deklarationen werden mit **;** getrennt

# Getter und Setter
Getter und Setter sind standardmässige Methoden auf einer Klasse um auf den Inhalt von [[Zugriffsmodifizierer#private|private]] [[Attribut|Attributen]] zugreifen zu können. 

[[Kopplung#Datenkapselung|Datenkapselung]] dadurch gegeben das durch die Getter und Setter Methoden die interne Implementation der Klasse verborgen wird. 

Getter und Setter sollten [[Schlüsselwörter#Final|finalisiert]] werden.

Sie sollte immer nur dann erstellt werden wenn sie wirklich gebraucht werden
- Nicht Standardmässig für jedes Attribut erzeugen sonst wir das Prinzip der [[Kopplung#Datenkapselung|Datenkapselung]] verletzt. 

Mit Getter Methoden kann man die Werte von [[Attribut|Attributen]] auslesen
Mit Setter Methoden kann man die Werte von [[Attribut|Attributen]] verändern
- Rückgabe ist immer void

Namensgebung
Getter: get*Attribut*(…)
Setter: set*Attribut*(…)
## Beispiele
Getter und Setter für den Vornamen und den Nachnamen einer Person
```java
public class Person {
	private String lastname;
    private String firstname;

   public String getLastname() {
        return lastname;
    }

    public void setLastname(String lastname) {
        this.lastname = lastname;
    }

    public String getFirstname() {
        return firstname;
    }

    public void setFirstname(String firstname) {
        this.firstname = firstname;
    }
}
```

