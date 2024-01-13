# if / else
If / else ist eine einfache Selektion welche je nach Bedingung den einen oder den anderen Programm block ausführt

- else ist optional
- Zu tiefe Verschachtelung von if Blöcken sollte nach Möglichkeit vermieden werden
	- Alternative: Verschachtelte If Statements in eigene Methoden auslagern
	- Aternative: [[Selektion#else if|else if]] Statement
## Aufbau
if (`<expression>`) then {…} else {…}

- Bedingung in (runden) Klammern
- Anweisungsblock in {geschweiften} Klammern

### Bedingung
- Die Bedingung muss ein boolsches Resultat (*true*/*false*) habe
	- Dafür werden oft  [[Operatoren#Logische Operatoren|Logische Operatoren]] verwendet
- Bedingungen können [[Operatoren#Verknüpfungen|verknüpft]] werden
- Bei Bedingungen sollte das Gesetz von [[Operatoren#Gesetz von De Morgan|Gesetz von De Morgan]] beachtet werden um die Ausdrücke so lesbar wie möglich zu behalten
- Wenn eine Variable bereits vom Typ `boolean` ist, kann man sie direkt als Expression verwenden 
	- `(variable)`
	- `(!variable)`
### Anweisungblock
- Wenn möglich immer den normalen Fall im Block vom `if` Statement und die Ausnahme im Block vom `else`

### Beispiel
Wenn a = 0 ist dann wird die eine [[Methode]] auf dem Objekt object ausgeführt, wenn a $\neq$ 0 wir eine andere [[Methode]] auf dem Objekt object ausgeführt

```java
if (a == 0) {
	object.doStuff()

} else {
	object.doOtherStuff()
}
```

## else if
Das else if Statement kann verwendet werden um eine zu tiefe Verschachtelung von If und Else Blöcken zu vermeiden

**Das funktioniert nur bei Bedingungen die einander ausschließen**
### Aufbau 
if (`<Bedingung 1>`) { …. }
else if (`<Bedingung 2>`) { …. }
else if (`<Bedingung 3>`) { …. }
else { …. }
### Beispiel
Wenn a = 0 ist dann wird die eine [[Methode]] auf dem Objekt object ausgeführt, wenn a = 1 wird eine andere [[Methode]] auf dem Objekt object ausgeführt und wenn a = 2 wird wieder eine andere [[Methode]] als in den ersten beiden Fällen ausgeführt.

```java
if (a == 0) {
	object.doStuff()

} else if (a == 1) {
	object.doThing()

} else if (a == 2) {
	object.doOtherThing()
}
```
# switch
Selektion basierend auf absolute Werte
- Eingeschränkt auf bestimmte [[Datentyp|Datentypen]] (byte, short, char, int, String, [[Enum|Enums]])


Wichtig bei Switch Statements: 
- Sobald ein Switch Zutrifft wird dieses abgearbeitet aber auch alle folgende Fälle
	- Will man das unterbinden verwendet man ***break;***
	- Seit Java 14 können auch `->` verwendet werden um das sogenannte Fall-Through zu unterbinden
- **Klassische Switch Statements sollten sehr sparsam gebraucht werden**
	- Code wird aufgebläht und ist schlecht wart-/erweiterbar
### Updated
In Java 14 gab es folgende Neuerungen um switch leistungsfähiger zu machen:

- Rückgabewert von switch kann in eine Variable gespeichert werden
	- `String daytype = switch (value) {...}`
- Fall Through kann ohne `break` mit `->` verhindert werden
	- `case 1 -> "Montag"`
- Codeblöcke sind nun möglich pro case (Rückgabe wert wir mit `yield` ausgegeben)
	- `case 1 -> { name = "Montag"; yield name;}`
- Mehrere Werte können zu dem selbe Case führen
	- `1,2,3,4,5 -> "Arbeitstag" `

## Aufbau 
### Beispiel
Basierend auf dem (int) Value wird die Variable “tag” mit einem String befüllt welcher ein Wochentag repräsentiert. 

#### Klassisch
Klassisch bestanden nur folgende Möglichkeiten:
```java
switch (value) {  
	case 1:  
		tag = "Montag";  
		break;  
	case 2:  
		tag = "Dienstag";  
		break;  
	case 6:  
		tag = "Samstag";  
		break;  
	case 7:  
		tag = "Sonntag";  
		break;  
	default:
		tag = "nicht erlaubte Tagnummer";
```

#### Updated (Java 14)
Mit Java 14 kamen diverse Neuerungen. In diesem Beispiel wird basierend auf dem value ausgegeben ob es sich bei dem Tag um ein Arbeitstag oder ein Wochenende handelt. Diese werte werden im String daytime gespeichert. Falls das value nicht ein gültiger Wochentag ist (z.B 8) wird hier noch [[Logging|geloggt]] um in dem Beispiel die Codeblöcke sinnvoll zu demonstrieren. 

```java
String daytype = switch (value) {  
	case 1, 2, 3, 4, 5  -> "Arbeitstag";  
	case 6, 7           -> "Wochenende";
	default             -> {
		LOG.info("{} ist kein gültiger Wochentag", value)
		yield "nicht erlaubt Tagnummer"
		}
```