- Obeserverpattern zum verhindern von zirkulären Beziehungen (starke [[OOP/Kopplung]])
- Beispiel: Ein Objekt will ein anderes Objekt darüber informieren das es einen Status Change gab


# Bausteine
- Listener der die Event Quelle registriert
- Even Quelle managed alle Listener
- Event Quell produziert und feuert Event
- Schnittstelle für den Funktionsaufruf

Folgende Dinge müssen implementiert werden:
- Listener Interfaces → verfügen über nur eine [[Methode|Methoden]]
- Event Objekt
- Folgende vier [[Methode|Methoden]]:
	- Registrierung eines Listeners für einen Event (auf Quelle) → public
	- Deregistrierung eines Listeners (auf Quelle) → public
	- [[Methode]] zur Verteilung (fire) eines Events (auf Quelle) → private
	- [[Methode]] für Notifikation des Events

## Best Practices
- Soweit wie möglich und sinnvoll immer Bestehende Eventklassen und Listener Interfaces  benutzen. 
- Behandlung von Events an private Methoden delegieren

### Namenskonvention
- *Xxx*Event → [[Klasse]] für das Event
- *Xxx*Listener(…) → [[Interface]] für den Listener
- add*Xxx*Listener(…) → Registrierung von Listener auf Quelle
- remove*Xxx*Listener(…) → Deregistrierung von Listener auf Quelle
- fire*Xxx*Event(…) → Versenden von Events auf Quelle
# Beispiel 
## ohne [[Lambdas]]
### Quelle
Methoden für die Registrierung, Deregistrierung und Verteilung des Events (auf der Quelle, hier Motor)
```java
public void addPropertyChangeListener(final PropertyChangeListener listener) {
    if (null != listener) {
        this.changeListeners.add(listener);
    }
}

public void removePropertyChangeListener(final PropertyChangeListener listener) {
    if (null != listener) {
        this.changeListeners.remove(listener);
    }
}

private void firePropertyChangeListener(PropertyChangeEvent event) {
    for (final PropertyChangeListener listener : this.changeListeners) {
        listener.propertyChange(event);
    }

}
```

[[Methode]] in welcher das Event erzeugt und fired wird (Hier das Anschalten von einem Motor)

```java
public void switchOn() {
    if (isSwitchedOff()) {
        this.motorState = MotorState.ON;
        final PropertyChangeEvent pcEvent = new PropertyChangeEvent(this, "state", MotorState.OFF, MotorState.ON);
        this.firePropertyChangeListener(pcEvent);
    }

}
```
### Listener
Listener implementiert Listener [[Interface]] (Hier Property Change Listener)

```java
public class Fahrzeug implements PropertyChangeListener { ... }
```

Methoden auf dem Listener (Fahrzeug) zum abhandeln der Motor Events (hier nur [[Logging]]). `propertyChange` wird hier vom [[Interface]] PropertyChangeListener geerbt (Java [[Interface]]).
Diese Code Beispiel könnte noch erweitert werden wenn das Fahrzeug von mehreren Quellen Events bekommen könnte. Dafür würde man einfach ein weiteres `ìf (event.getSource() == this.blaBla`

```java
    @Override
    public void propertyChange(final PropertyChangeEvent event) {
        if (event.getSource() == this.motor) {
            this.handleMotorEvent();
        }

    }
    
    private void handleMotorEvent(){
        LOG.info("The Motor State was changed");
    
    }
```

### [[Main Methode]] 
In der [[Main Methode]] werden hier die Objekte erzeugt und der Listener (fahrzeug1) wird auf der Quelle (motor1) registriert.

```java
 public static void main(final String[] args){
 
	final Motor motor1 = new Motor();
	final Fahrzeug fahrzeug1 = new Fahrzeug(motor1);

	motor1.addPropertyChangeListener(fahrzeug1);
 
}
```

### Eigene Events
Sollten die Java Built Events nicht reiche kann man auch eigene Events erstellen. Hier als Beispiel ein Event welches von EventObject erbt und zusätzlich ein [[Attribut]] für den Typ der Statisitk (hier ein [[Enum]]) hat und das ein [[Attribut]] um das Temperaturvalue zu speichern.

```java
public class TemperaturEvent extends EventObject {

    private Statistics type;
    private Temperatur value;

    public TemperaturEvent(Object source, Statistics type, Temperatur value) {
        super(source);
        this.type = type;
        this.value = value;
    }

    public Statistics getType() {
        return type;
    }

    public Temperatur getValue() {
        return value;
    }
}
```

### Eigene Listener [[Interface|Interfaces]]
Falls es kein passendens Listener [[Interface]] gibt kann man auch selbst eines erstellen. Dieses sollte wenn irgendwie möglich nur eine [[Methode]] haben, damit man das Ganze mit [[Lambdas]] vereinfachen kann. 

```java
@FunctionalInterface
public interface TemperaturStatisticsListener {
    
    public void newTemperatureStatistic(TemperaturEvent event);
    
}
```

## mit inneren [[Klasse|Klassen]]
Mit inneren Klassen müssen Events nicht mehr mit [[Selektion#if / else|if]] Konstruktionen geregelt werden, sondern es wird für jede Art von Quelle eine eigene innere [[Klasse]] definiert.

Da die Registrierung des Events nun aber in einer privaten [[Klasse]] stattfindet funktioniert das aufrufen innerhalb der Main [[Methode]] nicht mehr. Deshalb wird in diesem Beispiel der Listener im [[Konstruktor]] von Fahrzeug hinzugefügt.
```java
public class Fahrzeug {
	
	private Motor motor;
	private class MotorPropertyListener implements PropertyChangeListener {
		
		@Override
		public void propertyChange(final PropertyChangeEvent event) {
			handleMotorEvent();
		}
		
    
    }

	public Fahrzeug(Motor motor, Lampe lampe) {
        this.motor = motor;
        this.motor.addPropertyChangeListener(new Fahrzeug.MotorPropertyListener());
        
    }

	private void handleMotorEvent(){
        LOG.info("The Motor State was changed");
    }

}
```


## mit anonymen inneren Klassen
Mit anonymen inneren Klassen kann die Abhandlung des Events noch stärker verkürzt werden, in dem man bei der Registrierung des Events ein neues [[Interface]] instanziiert und dem gleich die Implementation seiner [[Methode]] mitgibt (Sonst kann man ein [[Interface]] nicht instanziieren). 


```java
public class Fahrzeug {
	
	private Motor motor;

	public Fahrzeug(Motor motor, Lampe lampe) {
        this.motor = motor;
        this.motor.addPropertyChangeListener(new PropertyChangeListener() {
            @Override
            public void propertyChange(final PropertyChangeEvent event) {
                handleMotorEvent();
            }

        });
        
    }

	private void handleMotorEvent(){
        LOG.info("The Motor State was changed");
    }

}
```

## mit [[Lambdas]]
Die kürzester Version ist die mit [[Lambdas]]. Hier erfolgt sehr viel implizit.
`addPropertyChangeListener` hat als [[Parameter]] Objekte vom ([[Interface]]) Typ `PropertyChangeListener`
Daher erwartert die [[Methode]] sowieso ein `PropertyChangeListener`. Dann muss man nur noch die Implementation mitgeben mit `handleMotorEvent()`

Diese sieht folgendermassen aus:
```java
public class Fahrzeug {
	
	private Motor motor;

	public Fahrzeug(Motor motor, Lampe lampe) {
        this.motor = motor;
        this.motor.addPropertyChangeListener(e -> handleMotorEvent());
        
    }

	private void handleMotorEvent(){
        LOG.info("The Motor State was changed");
    }

}
```

