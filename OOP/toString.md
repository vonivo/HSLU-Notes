Die toString ist auf jeder [[Klasse]] präsent weil jede [[Klasse|Klassen]] von Object [[Vererbung|erbt]]. 

- **Es ist Best Practice sie auf jeder Klasse zu überschreibe um eine sinnvolle Ausgabe erzeugen zu können.**
	- Die Implementation von Object gibt nur den Klassenname und den Hashcode aus was nicht sehr sinnvoll ist 

## Beispiele
```java
@Override
public String toString() {
	return "Temperature is " + this.temperatureCelcius + " C" 

}

@Override
public String toString() {
    return ("The element is called " + this.getBezeichnung());
}

// to String einer Subklasse welche sich auf die toString Methode der Oberklasse bezieht
@Override
public String toString() {
    return (super.toString() + " Achtung GIFTIG");
}
```
