Technische Systeme werden oft in mehrere Blöcke und Teilblöcke wegabstrahiert. Das Zusammenwirken dieser Blöcke wird dann mittels Input- und Outputdaten in einem Blockdiagram beschrieben.

## Blöcke
Die Blöcke in einem Blockdiagramm beschreibt ein Teil des Gesammtsystems:
Blöcke sind:
- Systeme oder Teilsysteme
- Softwarekomponenten
- Softwarebibliotheken
- Aufgaben/Funktionen
- externer Aktor (**Viereck in 3D**)
- externes System (**Strichmännchen**)![[Pasted image 20241229133151.png]]
Ein Block wird typischerweise als ein Rechteck mit einer Beschriftung dargestellt, es können jedoch auch symbole benutzt werden.

### Gruppierung
![[Pasted image 20241229133338.png]]
Falls mehrere Blöcke zusammengehören, kann dies durch eine Gruppierung visualisiert werden.
### Datenflüsse
Nachrichten/Datenflüsse zeigen auf, was sich für Daten zwischen den einzelnen Blöcken hin und her bewegen.

**Regeln:**
- Jede einzelne Nachricht wird als **Substantiv** formuliert.
- Pro Richtung wird **nur ein Pfeil** gezeichnet.
- Trennung der einzelnen Nachrichten mittels einem Komma.
 ![[Pasted image 20241229133608.png]]

### Beziehungen
Beziehungen sind dazu da, um zu visualisieren, welcher Block wen kennt.  Jede Beziehung hat dabei einen eindeutigen Namen.

**Beziehung**
![[Pasted image 20241229133840.png]]
**Gerichtete Beziehung**
![[Pasted image 20241229133855.png]]
=> Bankserver kennt Transfer nicht.

**ServicePort**
![[Pasted image 20241229133937.png]]
