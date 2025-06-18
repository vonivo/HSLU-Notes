>[!Definition]
>Ein Testdouble ist ein **Platzhalter** für eine echte, produktive Implementation während des Testings.

Testdoubles dienen dazu:
- Aufwand für [[Integrationtests mit JUnit|Integrationstests]] zu reduzieren.
- Selektivität von [[Integrationtests mit JUnit|Integrationstests]] zu verbessern.
- [[Integrationtests mit JUnit|Integrationstests]] in [[Unit Tests]] umzuwandeln.


## Anforderungen
- Damit Testdoubles verwendet werden können, muss **ein gutes Design** vorliegen.
- Der Einsatz von [[Interface|Interfaces]] lohnt sich fast immer. (z.B. echte Implementation und Test-Implementation)
- Die Wahl der genutzten Implementation muss zur Laufzeit auswählbar sein. [[Dependency Injection]]

## Arten
![[Testdoubles.png]]
### Dummy
Primitives Objekt. Meist ist ein Dummy eine leere Hülle (**funktionslos**), die als aktueller Parameter übergeben wird.

Ein Dummy wird verwendet, wenn der Parameter/Objekt für den Test zwingend notwendig ist, aber irrelevant.

### Stub
Einfache Implementation, welche mit möglichst **geringem** Aufwand **sinnvolle, vordefinierte** Werte zurückliefert.

Erlaubt sogenanntes **State-Testing** (State ist bei Stubs konstant)

### Spy
Alternative Implementation, welche **dynamische** Werte zurückliefert. Gleichzeitig merkt sich ein Spy exakt die Aufrufe der Methoden (Anzahl, Häuffigkeit, Parameter, Zeitpunkt, Exceptions)

Nach der Interkation kann ein Spy für die verifikation verwendent werden.

Erlauben **Behavior-Testing**

### Mock
**Spezialisierung des Spy**.
Kann zusätzlich die korrekte Interaktion selber verifizieren.

Mocks werden typisch mithilfe von speziellen Mock-Frameworks **zur Laufzeit** für jeden Testfall als **individuelles Mock-Objekt** erstellt.
- Verhalten wird dynamisch und somit programmatisch konfiguriert.

Ein Mock ist dem Spy sehr ähnlich. Einziger Unterschied ist der Ort
der Verifikation, Mocks sind dadurch spezifischer.


### Fake
Ein Fake ist eine **Alternative Implementation**, welche eine Komponenten mit vernünftigem Aufwand **vollständig** ersetzt.

Ermöglicht vollständige Entkopplung von einer Abhängigkeit.

## Empfehlung
## Dummy und Stub
Einfache Ersatzimplementationen um eine bessere Testisolation
zu erreichen. Mit geringem Aufwand erreicht man eine höhere
Selektivität und Stabilität der Testfälle. Einfach!

## Spy und Mock
«Universalwaffen» für Behavior-Testing mithilfe von Mocking-
Frameworks. Diese können auch zur Realisierung von Stubs und
Dummys genutzt werden. Komplexer.

## Fake
«Universalwaffen» für Behavior-Testing mit Hilfe von Mocking-
Frameworks. Diese können auch zur Realisierung von Stubs und
Dummys genutzt werden. Komplexer.