OSGI ist ein **leichtgewichtiges** Java Modul- und Servicesystem und definiert ein vollständiges [[Komponentenmodell]].
![[VSK/img/OSGI.png]]
OSGI ist verbreitet und wird z.B. von NetBeans, Confluence und Jira, etc. verwendet.

### Bundle
In OSGI ist Bundle die Bezeichnung von Komponenten bzw. Modulen.
- Komponenten sowie Schnittstellen werden als Bundles ausgeliefert.
- Ein Bundle wird immer als JAR mit einem Manifest`META-INF/MANIFEST.MF` ausgeliefert.

**Beispiel Manifest**
```yml
Manifest-Version: 1.0
Bnd-LastModified: 1616424844077
Build-Jdk-Spec: 11
Bundle-Activator: ch.hslu.vsk.textservice.ActivatorBundle
ManifestVersion: 2
Bundle-Name: Transform API (OSGi Variant)
Bundle-SymbolicName: ch.hslu.vsk.TransformApiBundle-Version: 1.0.0.SNAPSHOT
Created-By: Apache Maven Bundle Plugin
Export-Package: ch.hslu.vsk.textservice;uses:="org.osgi.framework";version="1.0.0"
Import-Package: org.osgi.framework;version="[1.4,2)"
Require-Capability: osgi.ee;filter:="(&(osgi.ee=JavaSE)(version=11))"
Tool: Bnd-5.1.1.202006162103
```
Im Manifest-File wird definiert, was exportiert wird und was die Requirements sind.

**Nur die Exportierten Packages** sind für andere Bundles ersichtlich -> **Eliminiert**  die Problematik, mit sich **überschneidenden Klassen und Methoden**.

=> Schnittstellen werden als separate Bundles ausgeliefert


### Isolation durch Eigene Classloaders
In OSGI wird für jedes Bundle ein eigener Classloader genutzt. So wird eine Art 'Namespace' für die verschiedenen Bundles erzeugt.
![[OSGI 1.png]]
- Dynamisches Laden von Modulen
- Ideal für Plugins (kein Neustart, aber keine garantierte Verfügbarkeit)
- Bundle wird via Bundleactivator benachrichtigt, wenn es aktiviert wird.

**Bundleactivator**:
```java
public class Activator implements BundeActivator {

  // Aufruf wenn Bundle aktiviert wird
  public void start(BundeContext context) {
    
  }

    // Aufruf wenn Bundle deaktiviert wird
  public void stop(BundeContext context) {
    
  }
}
```

### Service Registry
Die Service-Registry ist ein zentrales Verzeichnis, welches alle Services enthält:
![[OSGI3.png]]
Ein Service ist eine Objektinstanz, welche eine bestimmte API implementiert und
in der Registry publiziert wird.

**Service Registrieren**
```java
Hashtable<String, String> properties = new Hashtable<>();
properties.put("name", "Lowercase Transform");
context.registerService(TextService.class.getName(),
	new TextServiceImpl(), properties);
```

**Service finden**
```java
// Abrufen aller Service-Instanzen, die TextService implementieren:
ServiceReference[] refs = context.getServiceReferences(TextService.class.getName(),
                                                        null);
// Überprüfen, dass mindestens eine Service-Instanz gefunden wurde
if (refs.length == 0) throw new RuntimeException("not services found");
// Referenz zu erster gefundenen Service-Instanz
ServiceReference serviceReference = refs[0]
```

**Service verwenden**
ervices müssen vor Verwendung gepinned werden (sie sind volatil) und nach Verwendung freigegeben werden
```java
ServiceReference serviceReference = ...; // enthält Referenz zu Service
// Service-Instanz pinnen
TextService textService = (TextService) context.getService(serviceReference);
// Service-Instanz verwenden
output = textService.translate(text);
// Service-Instanz unpinnen
context.ungetService(serviceReference);
```

## Komponentenmodell

| Eigenschaft                    | Inhalt                                                                                             |
| ------------------------------ | -------------------------------------------------------------------------------------------------- |
| Schnittstellendefinition       | Java-Interfaces                                                                                    |
| Kommunikation und Verteilung   | Method Calls                                                                                       |
| Komposition und Auffindbarkeit | -Import/Export von Interfaces<br>- Service-Registry<br>- Isolation der nicht exportierten Packages |
| Deployment                     | - Einzelne JARs<br>- Bundle JAR                                                                    |
