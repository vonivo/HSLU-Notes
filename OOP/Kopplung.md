Kopplung bedeutet Abhängigkeit und Vernetzungen zwischen Klassen, Modulen, Systemen

**In der Objektorientierten Programmierung ist eine möglichst lose Kopplung das Ziel**
- Dadurch kann man Klassen leichter wiederverwenden
- Klassen können besser ausgetauscht werden

# Werkzeuge
## Datenkapselung
Wohlüberlegte Zugriffe auf Daten über Methoden (vgl. [[Methode#Getter und Setter|Getter und Setter]])
Datenkapselung wird mithilfe von [[Zugriffsmodifizierer|Zugriffsmodifizierern]] realisiert. 
So werden Attributen differenziert gekapselt was sie schützt vor unkontrollierter Manipulation. 

Siehe [[Zugriffsmodifizierer]]

### Best Practices
- **So verschlossen wie möglich so offen wie nötig**
- Standardmodellierung mit öffentlichen [[Methode#Getter und Setter|Getter und Setter]] und privaten [[Attribut|Attributen]] reicht nicht aus für gutes Design
	- Bewusstes Weglassen von [[Methode#Getter und Setter|Getter und Setter]] Methoden um Zugriff zu steuern
- [[Methode#Getter und Setter|Getter und Setter]] per IDE erstellen lassen und bewusst einsetzen
## Information Hiding
Bewusstes abstrahieren oder vollständiges “verstecken” der internen Repräsentation eines Objektes. 

- Erweitertes Konzept der Datenkapselung
- Wichtig sind nur die Methoden eine [[Klasse]], die Schnittstelle
- Möglichst einfache und schmale [[Interface|Schnittstellen]]
- Interne Realisation nicht wichtig
- [[Parameter]] und Rückgabewerte einer [[Methode]] sollten nicht zu viele über die interne Repräsentation preisgeben
- **Bei der Rückgabe von Objekten kein Referenz geben sondern eine Kopie**

# Beziehung zwischen Klassen
In aufsteigender Sträke:
- use / depends
	- Eine [[Klasse]] nutz einen anderen Typ
	- Z.B. als [[Lokale Variable]], formaler [[Parameter]], Returntyp, statischer Aufruf
- Assoziation
	- Explizite Beziehung zu einem anderen Typ (Beziehung ist essentiell)
	- Z.B als [[Attribut]]/Reverenz
- Aggregation
	- Ist Teil von…
	- Meistens [[Attribut]]
- Komposition
	- Wie Aggregation aber die [[Klasse]] erstellt das Teil
	- Das Teil ist nicht lebensfähig sonst
- Implementation
	- [[Interface]]
- [[Vererbung]]
	- Eine [[Klasse]] erbt von einer anderen [[Klasse]]