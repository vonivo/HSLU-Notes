Exceptiontesting ist der Prozess des Testens von Fehlermeldungen(Exceptions) die das Programm wirft. 

Basiert prinzipiell auf `JUnit5` und [[Unit Testing]]

# Aufbau
Exception Testing in JUnit 5 wird mithilfe von `assertThrows()` ausgewertet. 
`asserThrows()` bekommt eine [[Lambdas|Lamda]] Expression übergeben welche die zu testende Exception auslöst. 
Das wird in eine Variable gespeichert wer

## Beispiel
Testet ob eine Exception geworfen wird wenn das minimal Value eine Integers unterschritten wird
```java
    @Test()
    public void testAdditionIntTooSmall() {
        //act
        final Exception = assertThrows(RuntimeException.class, () -> {
            calc1.addition(Integer.MIN_VALUE, -1);
        });
        //assert
        assertEquals("Result out of bounds", resultat.getMessage());
    }
```
Testet ob eine Exception geworfen wird denn eine Temperatur zu tief ist
```java
  @Test
    public void temperatureTooSmall() {
        //act
        final Exception resultat = assertThrows(RuntimeException.class, () -> {
            Temperatur.createfromCelcius(-999);
        });
        //assert
        assertEquals("Not valid temperature!", resultat.getMessage());
    }
```