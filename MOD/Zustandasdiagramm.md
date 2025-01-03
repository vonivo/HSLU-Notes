Zustandsdiagramme definieren mögliche Folgen von Zuständen eines Objektes.

## Elemente
### Start und Ende
Jedes Zustandsdiagramm muss einen Start besitzen. Dieser Zustand besitzt **exakt** ein ausgehender Übergang und keine eingehende Übergänge.

Der Endzustand ist das Ende einer Verhaltensabfolge und besitzt keine ausgehenden Transitionen. 
![[Pasted image 20250103131346.png]]

### Zustand
Zustände, in denen sich Objekte einer Klasse befinden, werden als Rechteck mit abgerundeten Ecken modelliert.

- Hat eine eindeutige Bezeichnung.
- Kann drei Verhalten besitzen
	- entry-Verhalten -> Wird beim Betreten ausgeführt.
	- do-Aktivität -> Wird ausgeführt während das Objekt sich in dem Zustand befindet.
	- exit-Verhalten -> Wird vor Verlassen des Zustands ausgeführt.
- Das Symbol "o-o" Zeigt an, dass es für den Zustand ein Unterzustandsdiagramm gibt.

![[Pasted image 20250103131804.png]]
### Zustandsübergänge
Zustandsübergänge von einem Zustand in den nächsten werden Transitionen bezeichnet. Sie werde als gerichtet Pfeile modelliert.

Zustandsübergänge besitzen eine formale Beschreibung
- Werden durch ein **Ereignis** ausgelöst.
- Kann eine **Bedingung** haben.
- Kann mit einer **Aktion verbunden sein**.
![[Pasted image 20250103132015.png]]
### Ereignisse
- Singal-Event (Empfangen eines Signals (Button-Down, etc.))
- Change-Event (Bedingung wird wahr oder ein Zeitpunkt ist erreicht)
- Time-Event (Eine bestimmte Zeit ist abgelaufen)
- Call-Event (Objekt empfängt eine Nachricht (Methodenaufruf))

Wird bei einem Übergang das Ereignis weggelassen, wird dieser Übergang ausgeführt, sobald die do-Aktion fertig ist. Der Zustand **darf jedoch dann nur ein Ausgang haben**.![[Pasted image 20250103132308.png]]
### Aktivitäten / Aktionen
