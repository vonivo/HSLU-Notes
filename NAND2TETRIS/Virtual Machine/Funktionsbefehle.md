Im Allgemeinen gilt also, wenn eine Funktion (der **Caller**) eine Funktion (den **Callee**) aufruft, muss für folgenden Overhead gesorgt werden:
- Speicher der Rücksprungadresse.
- Speichern der Speicherressourcen des Callers.
- Zuweisung der vom Callee benötigten Speicherressourcen.
- Bereitstellung der vom Caller übergebenen Argumente für den Code des Callee.
- Beginn der Ausführung des Codes des Callee.

Analog wenn die Funktion fertig ist, muss folgender Overhead gemacht werden.
- Bereitstellung des Rückgabewerts des Calle für den Code des Callers.
- Recyclen der vom Callee verwendenten Speicherressourcen.
- Wiederherstellen der zuvor gespeicherten Speicherressourcen des Callers.
- Abrufen der zuvor gespeicherten Rücksprungadresse.
- Wiederaufnahme der Ausfürhung ab der Rpcksprungradresse des Codes des Callers.


## Aufruf Protokoll
Das Aufrufprotokoll ermöglicht es, primitive Befehle und Funktionsaufrufe nathlos miteinander zu verbinden:
`push x, push y, add, push 3, call power` -> $(x+y)^{3}$

Der Unterschied dabei ist:
- dass der Caller die Argumente auf den Stack legen muss,
- das Schlüsselwort `call` verwendet wird.
- Der Returnwert auch auf dem Stack-Landet.

**Beipsiel**: Berechnung der Hypotenuse
```
function main()
	push 3
	push 4
	call hypot
	return
	
function hypot(x,y)
	push x
	push x
	call mult
	push y
	push y 
	call mult
	add
	call sqrt
	return
	
....
```

## Stackframe
Bei jedem Funktionsaufruf muss dem oben beschriebenen Overhead Folge geleistet werden. Dazu wird pro Funktionsaufruf ein sogenanntes **Stackframe** auf den Stack gelegt welches so aussieht:
![[Pasted image 20260619094840.png]]

## Befehle
- `function functionName nVars`: Markiert den Beginn einer Funktion names `functionName`. Der Befehl teilt mit, dass die Funktion `nVars` lokale Variablen hat.
- `call functionName nArgs`: Ruft die benannte Funktion auf. Der Befehl teilt mit, dass `nArgs` Argumente vor dem Aufruf auf den Stack geschoben wurden.
- `return`: Übergibt die Ausführung an den Befehl, der im Code der Funktion, die die aktuelle Funktion aufgerufen hat, unmittelbar auf den `call`-Befehl folgt.

## Konventionen:
- Jede Funktion `functionname` in einer Datei `FileName.vm` muss `Filename.functionName` heissen. (Wird durch den [[Jack Compiler]] gemacht)
- Der Geltungsbereich des Funktionsnamens ist global.
- Der Programmeinstiegspunkt ist `Main.main`.
- `Main.main` ist argumentlos und wird durch `Sys.init` ([[Jack Betriebssystem]]) aufgerufen.

## Implementation

### Caller
- Vor dem Aufruf müssen `nArgs` auf den Stack gelegt werden.
- Aufruf von `call FileName.functionName nArgs`
- Nach Rückkehr des Callee sind die `nArgs` verschwunden uns es liegt nur noch der Return-Wert auf dem Stack.
- Speichersegments vom Caller sind nach Return dieselben.
### Callee
- Vor der Ausführung wurden Argumente auf den Stack gelegt.
- `LOCAL` Segment wurde zugewiesen und mit 0 initialisiert.
- `STATIC` Segment wurde auf das statische Segment der VM-Datei gesetzt.
- Arbeitsstack ist leer
- `THIS, THAT, POINTER, TEMP` sind noch undefiniert.
- Vor Rückgabe muss der Return-Wertauf den Stack. 

### `call f nArgs`
```
// erzeuge ein Label und schiebe es auf den Stack PSEUDO
push rAdd
push LCL
push ARG
push THIS
push THAT
// positioniere ARG und LCL neu
ARG = SP - 5 - nArgs
LCL = SP
goto f
// fügt das Rückkehrlabel in den Code
(rAddr)


// ASM
// push return-address  
@f$ret.0  
D=A  
@SP  
A=M  
M=D  
@SP  
M=M+1  
  
// push LCL  
@LCL  
D=M  
@SP  
A=M  
M=D  
@SP  
M=M+1  
  
// push ARG  
@ARG  
D=M  
@SP  
A=M  
M=D  
@SP  
M=M+1  
  
// push THIS  
@THIS  
D=M  
@SP  
A=M  
M=D  
@SP  
M=M+1  
  
// push THAT  
@THAT  
D=M  
@SP  
A=M  
M=D  
@SP  
M=M+1  
  
// ARG = SP - nArgs - 5  
@SP  
D=M  
@7 // 2 + 5  
D=D-A  
@ARG  
M=D  
  
// LCL = SP  
@SP  
D=M  
@LCL  
M=D  
  
// goto f  
@f  
0;JMP  
  
(f$ret.0)
```

### `function f nVars`
```
// fügt Funktionseinstiegslabel in den Code 
(f)
// initialisiert nVars lokale variablen auf 0
push 0
push 0
...
push 0


// ASM
(Filename.f)
// local 0 = 0  
@SP  
A=M  
M=0  
@SP  
M=M+1
```

### `return`
```
frame = LCL // frame ist temp Variable
rAdd = *(frame-5)
// setze die Werte für den Caller
*ARG = pop()    // Rückagbe wert
SP = ARG + 1    // Stackpointer
THAT = *(frame-1)
THIS = *(frame-2)
ARG = *(frame-3)
LCL = *(frame-4)
goto rAdd

// ASM
@LCL  
D=M  
@R13          // speichere LCL ind R13 (speichere frame)
M=D

@5  
A=D-A  
D=M  
@R14         // speicherer Rücksprungadresse in R14
M=D

@SP  
AM=M-1      // Pop Return Wert
D=M

@ARG  
A=M  
M=D

@ARG  
D=M+1  
@SP  
M=D

// Restore THAT
@R13  
AM=M-1  
D=M  
@THAT  
M=D 

// Restore THIS
@R13  
AM=M-1  
D=M  
@THIS  
M=D

// Restore ARG
@R13  
AM=M-1  
D=M  
@ARG  
M=D

// Restore LCL
@R13  
AM=M-1  
D=M  
@LCL  
M=D

// jump back
@R14  
A=M  
0;JMP
```


## Standard VM Zuordnung auf der [[Hack Maschine]]

| Symbol                                  | Verwendung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `SP`                                    | Dieses Symbol zeigt auf die RAM-Adresse, die direkt auf die Adresse folgt, die den obersten Wert des Stacks enthält.                                                                                                                                                                                                                                                                                                                                                                              |
| `LCL, ARC, THIS, THAT`                  | Diese Symbole verweisen jeweils auf die Basis RAM-Adressen der virtuellen Segmente `local, argument, this` und `that` der aktuell laufenden VM Funktion                                                                                                                                                                                                                                                                                                                                           |
| `Xxx.i `<br>(statische Variablen)       | Jeder Verweis auf `static i` in der Datei `Xxx.vm` wird in das Assembler Symbol `Xxx.i` übersetzt. Der Assembler weist diese symbolischen Variablen dem RAM zu, beginnend bei Adresse 16                                                                                                                                                                                                                                                                                                          |
| `functionName$label` (Ziele von goto)   | Sei `foo` eine Funktion in der Datei `Xxx.vm`. <br>Die Verarbeitung jedes `label bar` Befehls innerhalb von `foo` erzeugt das Symbol `Xxx.foo$bar` und injiziert es in den Assemblercode. Bei der Ubersetzung von `goto bar` und `if-goto bar` Befehlen in `foo` muss das Label `Xxx.foo$bar` anstelle von `bar` verwendet werden                                                                                                                                                                 |
| `functionName` (Einstiegspunkte)        | Bei der Verarbeitung jedes `function foo` Befehls in der Datei `Xxx.vm` wird ein Symbol `Xxx.foo` in den Assemblercode injiziert, das den Einstiegspunkt in den Funktionscode markiert. Danach übersetzt der Assembler dieses Symbol in die physikalische Adresse, an der der Funktionscode beginnt                                                                                                                                                                                               |
| `functionName$ret.i `(Rucksprungpunkte) | Sei foo eine Funktion in der Datei `Xxx.vm`. Bei der Verarbeitung jedes `call` Befehls in `foo` wird ein Symbol `Xxx.foo$ret.i` in den Assemblercode injiziert, wobei `i` eine laufende Ganzzahl ist (ein solches Symbol wird für jeden Aufrufbefehl in `foo` erzeugt). Dieses Symbol wird verwendet, um die Rücksprungadresse im Code des Caller’s zu setzen. Danach übersetzt der Assembler das Symbol in die physische Speicheradresse des Befehls, der unmittelbar auf den Aufrufbefehl folgt |
