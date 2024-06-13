Der optimierte Suchautomat macht sich einen [[Automaten]] zunutze, welcher spezifisch auf das Pattern $p$ abgestimmt ist, sodass die Zeichenkette sequenziell [[Suchalgorithmen|durchsucht]] werden kann.

## Beispiel
Das binäre Pattern "101011" wird gesucht. Dann lässt sich folgender Automat bauen:
![[OptimierterSuchautomat.png]]

| Zustand | Teilpattern     |
| ------- | --------------- |
| $z_{0}$ | nichts gefunden |
| $z_{1}$ | 1               |
| $z_{2}$ | 10              |
| $z_{3}$ | 101             |
| $z_{4}$ | 1010            |
| $z_{5}$ | 10101           |
| $z_{6}$ | 101011          |

## Implementation
```java
public int search(String a) {
	int state = -1
	int i = 0;
	do {
		switch(state) {
			case -1:
				if (1 == a.charAt(i)) {
					state = 1;
				}
				break;
			case 1:
				if (0 == a.chartAt(i)) {
					state = 10;	
				} else {
					state = -1;
				}
				break;
			case 10:
				if (1 == a.chartAt(i)) {
					state = 101;	
				} else {
					state = 1;
				}
				break;
			case 101:
				if (0 == a.chartAt(i)) {
					state = 1010;	
				} else {
					state = 1;
				}
				break;
			case 1010:
				if (1 == a.chartAt(i)) {
					state = 1011;	
				} else {
					state = -1;
				}
				break;
			case 10101:
				if (1 == a.chartAt(i)) {
					state = 1010;	
				} else {
					state = 1010;
				}
				break;
		}
		i++;
	} while (i < a.length && state != 101011)
	if (state = 101011) {
		return i - "101011".length;
	}
	return -1;
}
```

## Analyse
Der optimierte Suchautomat berücksichtigt, dass beim Pattern nicht immer von vorne wieder gesucht werden muss, sprich er merkt sich, was des Patterns schon gefunden wurde und ob man dort anknüpfen kann.

Der Ideal-Pfad entspricht einem [[Endliche Automaten#Deterministischer endlicher Automat|DEA]] welcher als [[Formale Sprache|Sprache]] genau ein Wort definiert.

Mit dem Zustandsautomaten kann eine Zeichenkette **rein sequenziell** durchsucht werden.
=> Kein Zeichen wird doppelt verglichen.

=> [[AD/Algorithmen/Komplexität|Komplexität]] vom $O(n)$.