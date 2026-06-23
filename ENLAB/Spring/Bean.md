Ein Spring-Bean ist ein POJO (plain old Java object) mit Spring Meta Daten.

Spring Beans werden vom **Spring-Container** erstellt und gemanaged.

## Spring Container
Der Spring Container (ApplicationContet/IoC-Container) ist zentraler Bestandteil von Spring. Der Container erzeugt Objekte und verwaltet diese. Dabei ist er zuständig für:
- wann sie erstellt werden
- ob es einen Singleton oder Prototype ist
- wann sie wieder aufgeräumt werden müssen
- Auflösung von Abhängigkeiten.

## Scope
### Singleton
Immer dieselbe Instanz, es existier nur eine. (Standard)
```java
@Bean
@Scope("singleton")
public HelloWorld helloWorldBean() {
	return new HelloWorld();
}

@Test void helloWorld() {
	Object a = ctx.getBean("helloWordBean");
	Object b = ctx.getBean("helloWordBean");
	assertThat(a).isSameAs(b);
}
```
### Prototype
Es wird immer ein neues Objekt erzeugt, wenn das Bean irgenwo injiziert wird:
```java
@Bean
@Scope("prototype")
public HelloWorld helloWorldBean() {
	return new HelloWorld();
}

@Test void helloWorld() {
	Object a = ctx.getBean("helloWordBean");
	Object b = ctx.getBean("helloWordBean");
	assertThat(a).isNotSameAs(b);
}
```

### Weitere
- Request
- Session
- Applicatoin
- Websocke
Diese Scopes existieren nur im Webstack.


## Explizite Definition
Die explizite Definition eines Spring-Beans wird mit der `@Bean`-Annotation auf einer Methode gemacht. Diese Methode muss sich innerhalb einer Klasse befinden, welche mit `@Configuration` annotiert ist.

Man verwendet die explizite Definition für Klassen welchem einem nicht gehören.

## Implizite Definition
Die implizite Definition wird mit `@Component`/`@Service`/`@Repository` auf einer Klasse gemacht. Das Bean wird dann über den **ComponentScan** automatisch gefunden (falls es in einem Subdirectory der ApplicationClass ist). Ansonsten können auch weitere Packages zum Component-Scan hinzugefügt werden.

Die Implizite Konfigruation wird verwendet, wenn einem der Code gehört.

## Component Identification
Per default wird der kleingeschriebene Name der Klasse zur Identifikation eines Beans verwendent.
```java
@Component
public class MyServiceImpl implements MyServvice {}

@Component
public class MyOtherServiceImpl implements MyService {}
```
werden zu `myServiceImpl` und `myOtherServiceImpl`.

Wenn bei der Injection nicht klar ist, welches Bean injiziert werden muss, gibt es einen `UnsatisfiedDependencyExpcetion`.

## @Autowired
Um Dependcies zu Inijizieren kann `@Autowired` verwendet werden. Es kann Konstruktor-, Feld- und Methoden-Injizierung verwendet werden. Um genauer zu spezifizieren, welches Bean verwendet wird kann die Annotation `@Qualifier` verwendet werden.

Autowired löst Beans folgendermassen auf:
1. Unique Bean Type
2. Verwende `@Qualifier` wenn verfügbar
3. Suche ein passendes Bean mit dem Namen der Variable.
