Als Unit Testing bezeichnet man das Testen von einem Softwarekomponenten. Dabei testet man nur eine [[Methode]], [[Klasse]] bzw. Einheit. Unit Tests sollte klein, übersichtlich, einfach, schnell ausführbar und einfach automatisierbar sein. 

Wichtig:
- Aussagekräftige Test
- Wohlüberlegte Testdaten

Getestet werden sollten:
- beliebige zufällige Daten (Normalfälle)
- vorsortierte Daten, keine Daten (Sonderfälle)
- ungültige, nicht sortierbare Daten (Ausnahmefälle)

Framework fürs testen: `JUnit`
- Aktuelle Version JUnit 5

Ein Testfall wird immer mit `@Test` annotiert
- Eine weitere Annotation ist `@Disabled` welche einen Test nicht ausführt ihn aber explizit als Skipped ausweist. 
## Best Pracitces
- Besser viele kleine Testmethoden als wenige grosse
- Möglichst wenige `asser*()` Statements pro Testmethode
- Nie nur für Testbarkeit Schnittstellen oder Sichtbarkeit ändern
- Testen während der Implementation um sichergehe zu können das es funktioniert

## Triple A pattern
Arrange:
- Erstellen der Testobjekte/daten
Act:
- Manipulieren der Testobjekte/daten
Assert
- Verifikation der Ergebnisse (mit assert* -Methoden)

```java
 @Test
    public void testAdditionPositive() {
        //act
        var resultat = calc1.addition(1, 5);
        //assert
        assertEquals(6, resultat);
    }
```

### Assert
Mit den `org.junit.jupiter.api.Assertions` kann man einen Test validieren:
Am meisten wird ``AssertEquals`` gebraucht welches verlgleicht ob zwei Wert gleich sind. 
- **Wichtig: immer das Expected Resultat zuerst aufschreiben**
Mit ``AssertTrue`` oder ``AssertFalse`` kann überprüft werden ob eine Bedingung wahr oder falsch ist

```java
assertEquals(-4, resultat);
assertEquals("Name: Steve Stevenson, Id Number: 123456", person.toString());
assertEquals("Stevenson", person.getLastname());
assertTrue(person.equals(new Person(123456, "Steve", "Stevenson")));
```
## Naming Convention
- Testklassen:
	- Heissen immer *[[Klasse]]*Test
	- Beispiel: TemperaturTest
- Testmethoden:
	- heissen immer test*MethodenName***spezifischere Beschreibung**(…)
	- Beispiel: testAdditionPositive(…)

## F.I.R.S.T Prinzipien
- Fast
	- Damit man Tests jederzeit und regelmässig ausführt
- Independent
	- Damit sie in beliebiger Reihenfolge und einzeln ausgeführt werden können
- Repeatable
	- In jeder Umgebung lauffähig
- Self-Validating
	- Ein einfaches boolsches Resultat
- Timely
	- Rechtzeitig vor dem produktiven Code geschrieben

## Test First
- Immer vor der Implementation die Testfälle schreiben

## Qualitätssicherung
- Messend der Codeabdeckung

# [[Equals & Hashcode]] Testen

Um eine Equals [[Methode]] zu testen sollte man folgende Fälle durchprüfen: 
1. Identität
2. Falsche/fremde [[Klasse]]
3. null - Werte in den einzelnen Attributen
4. Value Gleichheit für ein beliebiges [[Attribut]]

Ebenfalls kann man mithilfe des Equalverifiers testen, welcher den Equal Contract überprüft.
## Beispiele
Testen der [[Equals & Hashcode|Equals und Hashcode]] [[Methode]] von einem Punkt: 
```java

// Test mithilfe des Equal Verifiers (Warning für non final fields wird suppressed weil es nicht sinnvoll ist die Felder final zu machen)

    @Test
    public void equalsTest() {
        EqualsVerifier.forClass(Point.class).suppress(Warning.NONFINAL_FIELDS).verify();
    }

// Testen zweier Punkte die nicht gleich sind
    @Test
    public void equalsTestFalse() {
        Point point = new Point(1, 2);
        assertFalse(point.equals(new Point(3, 4)));
    }

// Testen zweier Punkte die Value gleich sind
    @Test
    public void equalsTestTrue() {
        Point point = new Point(1, 2);
        assertTrue(point.equals(new Point(1, 2)));
    }

// Testen der Hashcodes zweier Punkte die gleich sind
    @Test
    public void hashCodeTestTrue() {
        Point point = new Point(1, 2);
        assertEquals(point.hashCode(), new Point(1, 2).hashCode());

    }

// Testen der Hashcodes zweier Punkte die nicht gleich sind
    @Test
    public void hashCodeTestFalse() {
        Point point = new Point(1, 2);
        assertNotEquals(point.hashCode(), new Point(2, 3).hashCode());

    }


```

Testen der [[Equals & Hashcode|Equals und Hashcode]] [[Methode]] von einem Chemischen Element (Class Types)): 
```java
    @Test
    public void equalsTest() {
	    EqualsVerifier.forClass(ChemicalElement.class).usingGetClass().withIgnoredFields("siedepunkt", "schmelzpunkt", "bezeichnung", "abkuerzung").verify();
    }
    
    @Test
    public void equalsTestTrue() {
        ChemicalElement element = new Quecksilber();
        assertTrue(element.equals(new Quecksilber()));
    }

    @Test
    public void equalsTestTrueElement() {
        Quecksilber element = new Quecksilber();
        assertTrue(element.equals(new Quecksilber()));
    }

    @Test
    public void equalsTestFalse() {
        ChemicalElement element = new Quecksilber();
        assertFalse(element.equals(new Blei()));
    }

    @Test
    public void hashCodeTestTrue() {
        ChemicalElement element = new Quecksilber();
        assertEquals(element.hashCode(), new Quecksilber().hashCode());
    }

    @Test
    public void hashCodeTestFalse() {
        ChemicalElement element = new Quecksilber();
        assertNotEquals(element.hashCode(), new Blei().hashCode());
    }
 
```

# [[compareTo & Comparable]] Testen

## comparable Beispiel
```java
@Test
    public void compareTestFirstBigger() {
        Person person1 = new Person(654321, "Joanna", "Doe");
        Person person2 = new Person(123456, "Steve", "Stevenson");
        assertEquals(1, person1.compareTo(person2));
    }

    @Test
    public void compareTestSecondBigger() {
        Person person1 = new Person(123456, "Steve", "Stevenson");
        Person person2 = new Person(654321, "Joanna", "Doe");
        assertEquals(-1, person1.compareTo(person2));
    }

    @Test
    public void compareTestBothEqual() {
        Person person1 = new Person(123456, "Steve", "Stevenson");
        Person person2 = new Person(123456, "Steve", "Stevenson");
        assertEquals(0, person1.compareTo(person2));
    }
```
## Comparator Beispiel
```java 
  @Test
    public void compareToTestFirstBefore() {
        Person person1 = new Person(654321, "Joanna", "Doe");
        Person person2 = new Person(123456, "Steve", "Stevenson");
        
        assertEquals(-15, new PersonNameComparator().compare(person1, person2));
    }

    @Test
    public void compareToTestSecondBefore() {
        Person person1 = new Person(123456, "Steve", "Stevenson");
        Person person2 = new Person(654321, "Joanna", "Doe");
        
        assertEquals(15, new PersonNameComparator().compare(person1, person2));

    }

    @Test
    public void compareToTestEqual() {
        Person person1 = new Person(432121, "Steve", "Stevenson");
        Person person2 = new Person(123456, "Steve", "Stevenson");
        
        assertEquals(0, new PersonNameComparator().compare(person1, person2));

    }

```

# [[Exceptiontesting]]
Siehe [[Exceptiontesting]]