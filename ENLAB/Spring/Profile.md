>[!Definition]
>Ein Spring [[Bean]] kann einem Profil zugeordnet werden, welches wiederum aktiviert/deaktiviert werden kann. Das Standardprofil ist immer aktiv.

```java
@Configuration
@Profile("dev")
public class DevConfig {
}

@Configuration
@Profile("cloud")
public class CloudConfig {
}

@Configuration
@Profile("prod")
public class ProdConfig {
}
```

Profile können über `-Dspring.profiles.active=embedded,dev` aktiviert werden.
Für Tests gibt es die Annotation `@ActiveProfiles`
