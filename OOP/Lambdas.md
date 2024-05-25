Realisiert funktionale Programmierung innerhalb von Java und verfolgt einen deklarativen Ansatz anstatt einem imperativen. Vor allem bei der Verarbeitung von Daten als Datenströmen ([[Streams]])) sehr attraktiv.

Lamdbas funktonieren nur mit [[Interface#^ebc981|funktionalen Interfaces]] 
- Diese sind meist schon in Java vorhanden

Lamdbas unterscheiden sich nur durch die Anzahl und Reihenfolge der [[Parameter]] und dem Rückgabewert

Lamdbas können auch in [[Attribut|Attributen]] und [[Lokale Variable|Lokalen Variablen]] gespeichert werden

Es besteht kein Zwang zur Nutzung von Lamdbas

## Best Practices
- Lamdbas machen nur Sinn wenn sie kurz und kompakt sind
- Code sollte trotzdem Aussagekräftig bleiben
# Aufbau
Lamda Expression sehen folgendermassen aus `(<Parameter) -> {<implementation>}`
- Die [[Parameter]] beziehen sich auf die Anonyme Funktion 
- Die Implementation bezieht sich auf die einzige [[Methode]] des funktionalen [[Interface]].


## Beispiel 
```java
//Lamda Funktion welche zwei Long Werte addiert:
(long x, long y) -> {return x + y;}

//Lamda Funktion welche zwei beliebige Werte(polymorph) addiert, welche die Addition Operation kennen
(x,y) -> {return x+y;}

// Möglich Schriebweise für Lamda Funktion mit nur einem Ausdruck
(x,y) -> x+y

// Lamda Funktion mit nur einem formalen Parameter
x -> x * 2

//Lamda Funktion ohne Parameter
() -> this.Something()

// Lamda Funktion wenn die Parameter vom Lamda mit der Methode darin korrelieren (siehe unten für zweites Beispiel)
this::doSomething
```

### this::doSomething Beispiel
Folgendes Beispiel:
```java
this.motor.addPropertyChangeListener(this::handle)
```
- addPropertyChangeListener verlang PropertyChangeListener [[Interface]]
- Property Change Listener [[Interface]] hat eine [[Methode]] welche ein PropertyChangeEvent verlangt
- handle erwartet hier ebenfalls ein Property ChangeEvent, deshalb kann man diese Schreibweise verwenden


### Beispiel [[compareTo & Comparable#Comparator|Comparator]] mit Lamdbas
Das Comparator Interface kann ebenfalls mit Lamdbas implementiert werden. 

Hier speichern wir den Comparator des Nachnamen auf einem Attribut der Person
```java
private static final Comparator<Person> namecomp = (p1, p2) -> p1.getLastname().compareTo(p2.getLastname());
```

Diese kann dann folgendermassen (über ein [[Methode#Getter und Setter|Setter]]) aufgerufen werden und genutzt werden um eine Liste von Personen (siehe [[OOP/Datenstruktur]]) zu sortieren. 

```java
Collections.sort(personlist, Person.getLastNameComparator());
```