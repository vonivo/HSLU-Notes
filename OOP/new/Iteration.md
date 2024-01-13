Iteration werden verwendet um repetitive Aufgaben durchzuführen, wie z.B. eine Menge von Objekte bearbeiten/einlesen/ausgeben

- Iterationen werden auch Schleifen genannt
- Iterationen werden so oft ausgeführt bis eine logische [[Selektion#Bedingung|Bedingung]] erfüllt ist


Schleifenunterscheidung:
 - Schleifen mit Eingangstest:
	 - while
	 - for
- Schleifen mit Ausgangstet
	- do-while
	
- Schleifen mit einer bekannten Anzahl Iterationen
	- for
- Schleifen mit einer unbekannt Anzahl Iterationen
	- meisten while und do-while

## Best practices 
- Nicht auf absolute Werte Vergleichen sondern auf Bereich
	- Anstatt (x == 10) → (x > ==)
	- Aufpassen auf [[Datentyp#Fliesskommazahlen|Fliesskommazahlen]] das es zu Rundungsfehlern kommen kann
- Laufzeit beachten (Bei Schleifenkörper, Bedingung, Initialisierung und Finalisierung)
	- Die Methoden werden n-fach ausgeführt 
	- Gegebenenfalls Wert zwischenspeichern
- ***break*** und ***continue*** Anweisungen vermeiden (entspricht einem go to)
	- Stattdessen ein If Statement verwenden

# while
- Bedingung muss ein boolesches Resultat geben: solange diese ***true*** ist wird der Schleifenkörper ausgeführt
- Häufig werden die Variablen während dem Schleifenkörper verändert
- Evaluiert die Bedingung am Anfang bereits ein ***false*** wird der Schleifenkörper nie ausgeführt
- Bedingungen können auch Zuweisungen enthalten (verpönt aufgrund schlechter Lesbarkeit)
- Anzahl Iterationen in der Schleife sind meistens nicht bekannt
- Bedingung wird immer **vor** Ausführung des Schleifenkörpers ausgewertet

## Aufbau

while(`<expression`) {`<statements>`}
### Beispiel
Solange a grösser als 0 ist wird das value von a ausgegeben und a um eins verkleinert

```java
while (a > 0)
{
	System.out.println(a);
	a--;
}
```

# do-while
-  Bedingung muss ein boolesches Resultat geben: solange diese ***true*** ist wird der Schleifenkörper ausgeführt
- Häufig werden die Variablen während dem Schleifenkörper verändert
- Bedingung wird immer **nach** Ausführung des Schleifenkörpers ausgewertet
	- **Der Schleifenkörper wird in jedem Fall einmal ausgeführt**

## Aufbau
do {`<expression>`} while (`<expression>`);
### Beispiel 
 Das value von a wird ausgegeben und  um eins verkleinert solange a grösser als 0 ist.
```java
do {
	System.out.println(a);
	a--;
}
while (a > 0);
```

# for
- Hat neben einer Bedingung eine Initialisierung und eine Finalisierung
	- Initialisierung
		- Schleifenvariable wird deklariert und initialisiert 
			- Schleifenvariable nur sichtbar innerhalb der Schleife
			- Schleifenvariable kann problemlos für mehrere Schleifen verwendet werden
	- Finalisierung
		- Veränderung der Schleifenvariable
	- Initialisierung und Finalisierung dürfen mehrere Anweisungen enthalten
		- Diese werden per **Komma** getrennt
- For Schleife ist ideal für einfache, zählende Schleifen
- Anzahl Schleifendurchläufe bekannt oder im Voraus berechenbar

## Aufbau
for (`<initialisierung>`; `<expression>`; `<finalisierung>`){`<statements>`}
### Beispiel
```java
for (a = 5; a > 0; a--)
{
	System.out.println(a);
}

```

# foreach
- Syntaktische Vereinfachung für [[Datenstruktur|Datenstrukturen]] (z.B Collections, Arrays) verwendet werden
- Kein spezielles Schlüsselwort: **for** wird gebraucht
## Aufbau
### Beispiel
```java
for (final Temperatur t: list)
{
	t.doSomething();
}
```