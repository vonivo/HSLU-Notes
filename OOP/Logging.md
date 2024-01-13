Eine einfache Schnittstelle um wichtige Informationen loggen zu können.

Logs können ausgegeben werden:
- Konsole
- File
- Netzwerk
- Cloudsysteme

Verwendetes Frame Work is `SLF4J`

Konfigurationsdateien findet man:
`./src/main/resources`
`./src/test/resources`

## Best Practices
- Jede [[Exceptionhandling|Exception]] im Rahmen ihrer Behandlung mindestens einmal Loggen
- Produktiv persistieren nur Errors und Warnings

# Aufbau
Um den Logger zu verwenden muss auf der [[Klasse]] eine [[Schlüsselwörter#Konstanten|Konstante]] erstellt werden. 
Auf diese können dann alle Log [[Methode|Methoden]] ausgeführt werden. 

## Beispiele
```java
// Import
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

// Erstellen des Loggers (innerhalb der Klasse)
private static final Logger LOG = LoggerFactory.getLogger(Main.class);

// Loggen einer Info
LOG.info("The Motor State was changed");
```