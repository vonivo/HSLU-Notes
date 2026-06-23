Spring Boot ist ein weiteres Framework, welches auf Spring basiert. Ziel von Spring Boot ist es die verschiedenen Spring-Frameworks möglichst einfach Nutzbar zu machen. Dies beinhaltet vor allem gut gewählt Standardkonfigurationen, damit der Entwickler mit minimalen Konfigurationsaufwand arbeiten kann.

Spring-Boot stellt verschiedene `starter-poms` zur Verfügung, welche nötige Dependencies laden und diese direkt selbst konfigurieren.

## @SpringBootApplication
Dies Eine Annotation mit welcher die Startklasse annotiert wird. Die Annotation ist eine Sammlung aus weiteren Annotationen, welche viel Konfigurationsaufwand abnehmen.

Die Wichtigsten Annotation welche `@SpringBootApplication` kummuliert sind:
- `@EnableAutoConfiguration`
- `@ComponentScan`
- `@SpringBootConfiguration`

## @SpringBootConfiguration
Alternative zu `@Configuration` welche aus dem Spring-Framework kommt.

## @EnableAutoConfiguration
Startet die automatische Konfiguration. Sehr mächtige Funktion um ein Spring-Modul automatisch zu konfigurieren.
Verwendet of:
- `@ConditionalOnClass`
- `@ConditionalonMissingBean`
- `@ConditionalOnProperty`
um fehlende Konfiguration zu definieren.