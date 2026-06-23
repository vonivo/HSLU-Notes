In Spring kann externe Konfiguration über `.properties` (key-value) oder  
`.yml` Files genutzt werden.

Diese Konfiugration kann über das Environment-Bean aufgerufen werden:
```java
@Bean
public HelloWordl helloWorld(Environment env) {
	return new HelloWorld(env.getProperty("greeting"));
}
```

Als alternative kann die Konfiguration mit `@Value` auch direkt in ein Field injiziert werden:
```java
@Value("{properityName:defaultValue"})
private String property;
```

Über das Environment Bean liefert Konfiguration von folgenden Quellen:
- System.getProperty
- System.getenv()
- Java Properties-Fiel / YAML Files

## application.yml / application.properites
Das Standard-Properties-File heisst application. Das File wird an folgenden Orten gesucht:
- `./config` relativ zum aktuellen Pfad
- `./` aktueller Pfad
- Classpath `/config` Package
- Classpath root `/`

Konfigurationen können überschrieben werden durch:
- Programmargumente
- Datei
- Classpath

`spring.config.name` kann eine Komma-separierte Liste sein
`spring.config.location` Ein Pfad zur Datei. 