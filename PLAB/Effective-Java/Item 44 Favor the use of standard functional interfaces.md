In Java existieren schon viele standardisierten funktionale [[Interface|Interfaces]]. Wo immer möglich, sollten diese für [[Lambdas]] benutzt werden.

## Vorteile:
- Macht API **einfacher zu erlernen** (da die Konzepte dieser Interfaces meist schon bekannt sind.)
- **Interoperabilität**, da viele dieser [[Interface|Interfaces]] default-[[Methode|Methoden]] zur Verfügung stellen.

## Typen von Functional-Interfaces
- **Operator** repräsentiert Funktionen, welche gleiche Argument- und Rückgabe-Typen haben
- **Predicate** repräsentiert Funktionen, welche basieren auf einem Argument ein `boolean` zurückgeben
- **Function** repräsentiert Funktionen, welche verschieden Return und Argument-Typen haben
- **Supplier** repräsentiert Funktionen, welche kein Argument entgegennehmen und einen Wert zurückgeben
- **Consumer** repräsentiert Funktionen, welche ein Argument entgegennehmen und keinen Retrunwert haben.

Für die primitiven Datentypen gibt es *Primitve Functional Interfaces*, welche in Bezug auf AutoBoxing / Unboxing optimiert sind.


## Eigene Functional Interfaces
Eigen Functional-[[Interface|Interfaces]] sollten geschrieben werden, wenn ein oder mehrere zutreffen:
- Es häufig genutzt wird und von einem beschreibenden Namen profitiert.
- Es einen starken Vertrag mit sich bringt.
- Wenn es von eigenen default-[[Methode|Methoden]] profitieren würde

Eigen Functional-[[Interface|Interfaces]] sollten immer mit `@FunctionInterface` gekennzeichnet werden:
- Andere Entwickler wissen, worum es sich handelt.
- Der Compiler zwingt den Programmierer dazu, ein SAM-Interface zu erstellen.
- Es verhindert das es im Nachhinein erweitert wird.
 

