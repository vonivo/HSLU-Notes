Die Stackmaschine ist eine [[Virtual Machine]] welche nur anhand eines Stack rechnet.

Der Stack kennt dabei natürlich push und pop und hat das LIFO-Prinzip:
![[Pasted image 20260618144214.png|398]]



Der Stack kennt dabei zwei Arten von Operationen:
- **binäre Operationen**: Benutzt die letzten 2 Argumente des Stacks.
	- `add`
	- `sub`
	- `or`
	- `and`
- **unäre Operationen**: Benutzt nur das letzte Argument des Stacks.
	- `neg`

## Befehle
Es gibt 4 Arten von Befehlen innerhalb der Stack-Machine:
1. **[[Push- und Pop-Befehle]]**: Übertragen Daten zwischen Stack und Speichersegmenten.
2. **[[Arithmetisch-logische Befehle]]**: führen arithmetische und logische Operationen aus.
3. **[[Verzweigungsbefehle]]**: ermöglichen bedingte und unbedingte Verzweigungsoperationen
4. **[[Funktionsbefehle]]**: ermöglichen Funktionsaufrufe und -rückgaben.

**Implementation**
Wenn ein Fix Basis Adresse für den Stack gewählt wird, kann der Stack mit einer einzigen Variablen implementiert werden. Diese Variable heisst `SP` (Stack-Pointer).
Dieser Pointer zeigt immer auf den nächsten unbelegten Stack-Platz.
**Push**
`RAM[SP] = x; SP++`
**Pop**
`SP--;x = RAM[SP]`

>[!Error]
>Die Stack-Base-Adresse auf der [[Hack Maschine]] ist **256** im RAM.

>[!Info]
>Die VM-Sprache ist bewusst von der HW-Plattform abstrahiert, dass sie auf jeder HW laufen könnte.
