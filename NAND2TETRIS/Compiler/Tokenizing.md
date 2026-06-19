>[!Definition]
>Tokenizing (lexikalische Analyse) erleichtert den Zugriff auf den Eingabestrom, indem dieser schrittweise in einzelne Tokens zerlegt wird.

Das Jack-Lexikon ([[JACK]]) besteht aus:
- **keywords**: `class`|`constructor`|`function`|`method`|`field`|`static`|`var`| `int`|`char`|`boolean`|`void`|`true`|`false`|`null`|`this`|`let`|`do`|`if`|`else`|`while`|`return`
- **symbols**:`{`|`}`|`(`|`)`|`[`|`]`|`.`|`,`|`;`|`+`|`-`|`*`|`/`|`&`|`|`|`<`|`>`|`=`|`~`
- **integers**: Eine dezimalzahl von 0 bis 32767
- **strings**; `"<folge von buchstaben>"`
- **identifiers** Folge von Buchstaben, Zahlen, Unterstrich, welche nicht mit einer Zahl starten.

## Analyzer
Analysiert das Programm und findet den dazugehörigen Typen pro Token:
![[Pasted image 20260619151408.png]]

## Parser
![[Pasted image 20260619151634.png]]
Der Syntak-Parser akzeptiert oder verwirft ein gegebenes Eingabeprogramm. Dabei erstellt er den Parsebaum des Programms.

### API
```java
class CompilationEngine {
	void compileLet() {
	 }

	void compileWhile() {
	}

	void compileTerm() {
	}

	// etc.
}
```

**Rekursives absteigendes Parsen**
- Der Parser ist als eine Menge von `compileXXX`-Methoden konzipiert.
- Das Design jeder `compileXXX`-Methode basiert auf einer entsprechenden Grammatikregel.
- Jede `compileXXX`-Methode ist dafür verantwortlich, ihren eigenen Teil der Eingabe weiterzulesen und zu verarbeiten.
- Die `compileXXX`-Methoden rufen sich gegenseitig rekursiiv auf.

## LL-Grammatik
>[!Info]
>Bei einer LL-Grammatik erfolgt das Parsen von links nach rechts, wobei eine linksseitige Ableitung der Eingabe durchgeführt wird.

- `LL(k)`: Ein Vorausblick auf `k` Tokens reicht aus, um zu wissen, welche Parsing-Regel als nächstes angewendet werden soll.
- `LL(1)`-Grammatiken lassen sich einfach und elegant mit rekursiven Abstiegparsern verarbeiten (kein Batracking nötig.)
- Die Jack-Grammatik ist eine `LL(1)` Grammatik, mit einer Ausnahme, die sich leicht handhaben lässt.
![[Pasted image 20260619153305.png]]
![[Pasted image 20260619153313.png]]

Laut der Definition von `term` und `subroutineCall` kann ein aktuelles Token, das ein `varName` ist, eine von fünf möglichen Formen annehmen:
- `foo`
- `foo[expression]`
- `foo(expressionList)`
- `Foo.bar(expressionList)`
- `foo.bar(expressionList)`
-> Dies ist der einzige Fall, in dem die Jack-Grammatik `LL(2)` ist.

## Implementation
### JackTokenizer

| Routine       | Arugments          | Returns                                                                                                                                       | Function                                                                                                                         |
| ------------- | ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Constructor   | input file/ stream |                                                                                                                                               | Opens the input file/stream and gets ready to tokenize it                                                                        |
| hasMoreTokens |                    | Boolean                                                                                                                                       | Do we have more tokens in the input?                                                                                             |
| advance       |                    |                                                                                                                                               | Gets the next token from the input and makes it the current token.                                                               |
| tokenType     |                    | KEYWORD, SYMBOL, IDENTIFIER, INT_CONST, STRING_CONST                                                                                          | Returns the type of the current token                                                                                            |
| keyWord       |                    | CLASS, METHOD, FUNCTION, CONSTRUCTOR, INT, BOOLEAN, CHAR, VOID, VAR, STATIC, FIELD, LET, DO, IF, ELSE, WHILE, RETURN, TRUE, FALSE, NULL, THIS | Returns the keyword which is the current token. Should be called only when tokenType() is KEYWORD                                |
| symbol        |                    | Char                                                                                                                                          | Returns the character which is the current token. Should be called only when tokenType() is SYMBOL.                              |
| identifier    |                    | String                                                                                                                                        | Returns the identifier which is the current token. Should be called only when tokenType() is IDENTIFIER.                         |
| intVal        |                    | Int                                                                                                                                           | Returns the integer value of the current token. Should be called only when tokenType() is INT_CONST                              |
| stringVal     |                    | String                                                                                                                                        | Returns the string value of the current token, without the double quotes. Should be called only when tokenType() is STRING_CONST |
### CompilationEngine
| Routine               | Arugments          | Returns | Function                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| --------------------- | ------------------ | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Constructor           | input file/ stream |         | Creates a new compilation engine with the given input and output. The next routine called must be compileClass()                                                                                                                                                                                                                                                                                                                                                                    |
| CompileClass          |                    |         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| CompileClassVarDec    |                    |         | Compiles a static declaration or a field declaration                                                                                                                                                                                                                                                                                                                                                                                                                                |
| CompileSubroutine     |                    |         | Compiles a complete method, function, or constructor.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| compileParameterList  |                    |         | Compiles a (possibly empty) parameter list, not including the enclosing ‘‘()’’.                                                                                                                                                                                                                                                                                                                                                                                                     |
| compileVarDec         |                    |         | Compiles a var declaration.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| compileStatements     |                    |         | Compiles a sequence of statements, not including the enclosing ‘‘{}’’                                                                                                                                                                                                                                                                                                                                                                                                               |
| compileDo             |                    |         | Compiles a do statement                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| compileLet            |                    |         | compileLet                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| compileWhile          |                    |         | Compiles a while statemen                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| compileReturn         |                    |         | Compiles a return statemen                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| compileIf             |                    |         | Compiles an if statement, possibly with a trailing else clause                                                                                                                                                                                                                                                                                                                                                                                                                      |
| CompileExpression     |                    |         | Compiles an expression                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| CompileTerm           |                    |         | Compiles a term. This routine is faced with a slight difficulty when trying to decide between some of the alternative parsing rules. Specifically, if the current token is an identifier, the routine must distinguish between a variable, an array entry, and a subroutine call. A single lookahead token, which may be one of `[`, `(`, or `.` suffices to distinguish between the three possibilities. Any other token is not part of this term and should not be advanced over. |
| CompileExpressionList |                    |         | Compiles a (possibly empty) comma-separated list of expressions.                                                                                                                                                                                                                                                                                                                                                                                                                    |
