1. Single Responsibility Principle (SRP).  
2. Don’t Repeat Yourself (DRY).  
3. Favor Composition over [[Vererbung|Inheritance]] (FCoI).  
4. Design for [[Vererbung|inheritance]], oder prohibit it.  
5. Achten Sie auf hohe [[Kohäsion]] und lose [[Kopplung]].  
6. Differenzieren Sie [[Kopplung#Datenkapselung|Datenkapselung]] von [[Kopplung#Information Hiding|Information Hiding]].  
7. Verwenden Sie [[Interface|Schnittstellen]] zur Entkopplung und Abstraktion.  
8. Testen Sie mit [[Unit Testing|Unit Tests]] nach dem [[Unit Testing#Test First|Test First]] Prinzip.  
9. Viele kleine Einheiten sind besser als wenige Grosse.  
10. Aussagestarke Namensgebung und formatierter Quellcode.

# SRP
- Eine [[Klasse]] hat möglichst eine Zuständigkeit
- Eine [[Klasse]] hat nur einen Grund zur Änderung
- Änderungen und Erweiterungen sollten sich immer auf möglichst wenige Klassen beschränken
- Viele kleinen [[Klasse|Klassen]] sind besser als wenige grosse

# DRY
- Duplizieren von Code vermeiden
- Einfache Duplizierung
	- Kopiere Codefragmente
- Subtile Duplizierung
	- Wiederholtem gleichartige Bedingungs-Konstrukte
	- Gleiche Algorithmen, unterschiedlich implementiert

- Lösung:
	- Objektorientierung, Funktionen, Design Patterns

# FCol
- Die Komposition (part-of) ist der [[Vererbung]] (is-a) vorzuziehen!
- Keine [[Klasse]] spezialisieren die nicht dafür vorgesehen ist
- Komposition ist wartungsfreundlicher

# Design for Inheritance of prohibit it
- Gute Basis Klassen designen oder sie [[Schlüsselwörter#Final|finalisieren]]

# Hohe [[Kohäsion]] und lose [[Kopplung]]
- Hohe [[Kohäsion]]
	- Das zusammenfassen was zussamengehört
- Lose [[Kopplung]]
	- So wenig und schwache Beziehungen wie möglich und so viele starke Beziehungen wie nötig
- Siehe [[Kopplung#Datenkapselung|Datenkapselung]] und [[Kopplung#Information Hiding|Information Hiding]]

# [[Kopplung#Datenkapselung|Datenkapselung]] und [[Kopplung#Information Hiding|Information Hiding]]
- [[Kopplung#Datenkapselung|Datenkapselung]]
	- Exlizierte und Bewusster Umgang mit [[Zugriffsmodifizierer|Zugriffsmodifizieren]]
	- [[Attribut|Attribute]] möglichst private
	- [[Methode|Methoden]] public oder private gut abwägen
- [[Kopplung#Information Hiding|Information Hiding]]
	- Schnittstelle und Implementation möglichst strikt trennen
	- Keine Rückschlüsse auf interne Implementation zu lassen

# Verwenden sie [[Interface|Schnittstellen]]
- Mittel zur Abstraktion
- Bessere Alternative als vollabstrakte Klassen
- Konzentration auf das **was** danach auf das **wie**
- Lieber zu viele Schnittellen als zu wenigen

# Testen mit [[Unit Testing|Unit Tests]] nach dem [[Unit Testing#Test First|Test First]] Prinzip
- Testen um fortlaufend die Gewissheit zu erhalten dass alles noch funktioniert
- Effizientes automatisierte selbst validiertes testen
- Vor der Implementation die Testfälle schreiben
- Kein Projekt und keine [[Klasse]] ist zu klein um nicht mit [[Unit Testing|Unit Tests]] getestet zu werden

# Viele kleine Einheiten sind besser als wenige Grosse
- Einheiten: Module, Packages, [[Klasse|Klassen]], [[Methode|Methoden]]
- Kleine Einheiten sind:
	- besser verwendbar
	- schneller verständlich
	- einfacher testbar
- Immer hinterfragen ob nicht eine Aufteilung sinnvoll wäre
- Refactoring ist ein ständiger Prozess
#  Aussagestarke Namensgebung und formatierter Quellcode
- Namen für Klassen und Methoden nie leichtfertig wählen
- Ein guter Name...  
	- hilft, den Sinn und die Absicht schneller zu verstehen.  
	- reduziert Aufwand für die Dokumentation.  
	- erhält die [[Kohäsion]] (weil man Verletzungen schneller erkennt)
- Quellcode immer sauber und automatisch korrekt formatiert