
| Befehl                  | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Leerraum und Kommentare | Leerzeichen, Zeilenumbrüche und Kommentare werden ignoriert. Die folgenden Kommentarformate werden unterstützt: `// Kommentar am Ende der Zeil`<br>`/* Kommentar bis zum Ende */` <br>`/** Richtet sich an Softwaretools, die API Dokumentation extrahieren.*/`                                                                                                                                                                                                                                                                                                                                                                                   |
| Symbole                 | `( )` werden zum Gruppieren von arithmetischen Ausdrücken und zum Einschliessen von Argumentlisten (in Unterprogrammaufrufen) und Parameterlisten (in Unterprogrammdeklarationen) verwendet. <br>`[ ]` werden für die Indizierung von Arrays verwendet.<br>`{ }` dient der Gruppierung von Programmeinheiten und Anweisungen.<br>`,` wird als Separator für Variablen Listen gebraucht.<br>`;` dient als Terminator von Anweisungen.<br>`=` dient als Zuweisungsoperator und als Vergleichsoperator.<br>`.` dient als Zugriffsoperator auf Mitglieder einer Klasse.<br>`+ - * / & \| ~ < >` sind Operatoren                                       |
| Reservierte Wörter      | `class, constructor, methode, function` für Programmkomponenten. <br>`int, boolean, char, void` für primitive Datentypen.<br>`var, static, field` für die Variablendeklaration. <br>`let, do, if, else, while, return` für Anweisungen.<br>`true, false, null` für Konstante Werte. <br>`this` für Objektreferenzen.                                                                                                                                                                                                                                                                                                                              |
| Konstanten              | - **Zahlenkonstanten** sind Werte von 0 bis 32767. Negative ganze Zahlen sind keine Konstanten sondern Ausdrücke des einstelligen Minus Operators, angewandt auf eine int Konstante. Der resultierende Bereich von Werten geht von -32768 bis 32767. <br>- **Zeichenketten** sind durch `"` eingeschlossene Zeichen. Alle Zeichen ausser ≪newline≫ und ≪double quote≫ sind erlaubt. Diese zwei Zeichen werden vom Betriebssystem mit den zwei Funktionen `String.newLine()` und `String.doubleQuote()` zur Verfügung gestellt. <br>- **Boolesche Konstanten** sind `true` und `false`. <br>- Die `null` Konstante bedeutet eine **Null-Referenz** |
| Bezeichner              | Bezeichner sind aus einer beliebig langen Folge von Buchstaben (`A-Z,az`), Ziffern (`0-9`) und dem Unterstrich `_` zusammengesetzt. Das erste Zeichen muss ein Buchstabe oder der Unterstrich `_` sein. Die Sprache unterscheidet zwischen Gross- und Kleinschreibung: x und X werden als unterschiedliche Bezeichner behandelt.                                                                                                                                                                                                                                                                                                                  |

## Unterprogramme
- **Methoden** sind so konzipiert, dass sie mit dem aktuellen Objekt arbeiten.
- **Funktionen** sind statische Methoden auf Klassenebene.
- **Konstruktoren** erzeugen neue Objekte des Klassentyps und geben diesen zurück.

Eine Unterprogrammdeklaration hat die folgende Struktur

```
Unterprogramm Typ Name(Parameterliste) {
	Dklaration lokaler Variablen
	Anweisungen
}
```
Paramterlisten sehen so aus: `(int x, boolean sign, Fraction g)`

### Aufrufe
**Funktions- und Konstruktoraufrufe**
- `className.functionName(exp1, exp2,...,exp3)`
- `className.constructorName(exp1,exp2,...,exp3)`

>[!Info]
>Der Klassenname muss immer angegeben werden, auch wenn die Funktion oder der Konstruktor in der gleichen Klasse wie der Caller ist.

**Methodenaufrufe**
- `varName.methodName(exp1, exp2,..., exp3)`
- `methodName(exp1, exp2,..., exp3)` oder `this.methodName(exp1, exp2,..., exp3)`

#### Beipsiel
```java
class Foo { 
	...
	method void f() { 
		/* Declares a local variable of class type Bar */ 
		var Bar b; 
		/* Declares a local variable of primitive type int */ 
		var int i; 
		...
		/* Calls function g of current class */ 
		do Foo.g(); 
		/* Calls function h of class Bar */ 
		do Bar.h(); 
		/* Calls method m of current class, on the this object */ 
		do m(); 
		/* Calls method q of class Bar, on object b */ 
		do b.q(); 
		/* Calls method w on the this object, calls method s of class Bar on object b, calls function or constructor t of class Foo */ 
		let i = w(b.s(),Foo.t());
```


## Variablen

| Typ                | Beschreibung                                                                                                                                                                              | Deklariert in | Geltungsbereich                          |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ---------------------------------------- |
| Statische Vairable | `static type varName;` <br>Von jeder statischen Variablen existiert eine Kopie, die von allen Unterprogrammen der Klasse gemeinsam genutzt wird (wie private statische Variablen in Java) | Klasse        | Klasse, in der sie deklariert ist        |
| Feldvariable       | `field type varName;` <br>Jedes Objekt (Instanz der Klasse) hat eine private Kopie der Feldvariablen (wie Objektvariablen in Java)                                                        | Klasse        | Klasse, in der sie deklariert ist        |
| Lokale Variable    | `var type varName;` <br>Wird zu Beginn der Ausführung des Unterprogramms erstellt und bei der Rückkehr des Unterprogramms verworfen                                                       | Unterprogramm | Unterprogramm, in der sie deklariert ist |
| Parametervariable  | Stellen die Argumente dar, die an das Unterprogramm übergeben werden. Werden wie lokale Variablen behandelt, deren Werte durch den Caller des Unterprogramms initialisiert werden         | Unterprogramm | Unterprogramm, in der sie deklariert ist |

## Zeichenketten
Strings sind Instanzen der [[String-Klasse]].
```java
var String s;    // an object variable
var char c;      // a primitive variable
/* Sets s to the string object "Hello Wordl"*/
let s = "Hello World"M;
/* Sets c to 87, the integer character code fo 'W' */
let c = s.charAt(6);
```

## Anweisungen

| Anweisung | Syntax                                                                     | Beschreibung                                                                                                                                                                            |
| --------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `let`     | `let varName = expression;` <br>`let varName[expression1 ] = expression2;` | Eine Zuweisungsoperation. Zugelassen sind statische Variablen, Feldvariablen, lokale Variablen oder Parametervariablen                                                                  |
| `if`      | ```if (expression) {statements1 ; } else { statements2 ; }```<br>          | Typische if-Anweisung, mit einer opionalen else-Klausel. Die geschweiften Klammern sind obligatorisch, auch wenn es sich bei statements um eine einzelne Anweisung handelt.             |
| `while`   | ```while (expression){ statements; }```                                    | Typische while-Anweisung. Die geschweiften Klammern sind obligatorisch, auch wenn es sich bei statements um eine einzelne Anweisung handelt                                             |
| `do`      | `do function-call;`<br>`do method-call;`                                   | Wird verwendet, um eine Funktion oder eine Methode aufzurufen, wobei der zuruckgegebene Wert, falls ¨ vorhanden, ignoriert wird                                                         |
| `return`  | ``return expression;`<br>`return;`<br>                                     | Wird verwendet, um einen Wert aus einem Unterprogramm zurückzugeben. Die zweite Form muss von `void` Unterprogrammen verwendet werden. Konstruktoren müssen den Wert `this` zurückgeben |

## Ausdrücke / Expression
In Jack sind folgende Ausdrück möglich:
- Eine **Konstante**
- Ein **Variablenname** im Anwendungsbereich
- Das **Schlüsselwort** `this`
- Ein **Array Element** mit der Syntax `arr[expression]`, wobei `arr` ein Variablenname von Typ `Array` im Anwendungsbereich ist.
- Ein **Unterprogrammaufruf**, der nicht den Typ `void` zurückgibt.
- Ein Ausdruck, dem einem der **unären Operation** (`-`oder `~`) vorangestellt ist.
- Ein Ausdruck der Form `expression op expression`, wobei `op` einer der folgenden binären Operatoren ist `+,-,*,/,&,|,<,>,=`
- `(expression)` ein Ausdruck in **Klammern**


## Operatorpriorität
Die Priorität der Operatoren ist in Jack nicht festgelegt, ausser das Klammern zuerst kommen.

## Objektkonstrutkion
Die Objektkonstruktion erfolgt in zwei Schritten:
1. Deklariere eine Referenzvariable.
2. Rufe den Konstruktor der Klasse auf.

>[!Info]
>Konstruktoren können beliebige Namen haben.

**Beispiel**
```java
var Class a;
let a = Class.new(x,y,...);
```

## Objektentsorgung
Wenn ein Objekt nicht mehr benötigt wird, muss es entsorgt werden.
```java
Memory.deAlloc(c)
```

