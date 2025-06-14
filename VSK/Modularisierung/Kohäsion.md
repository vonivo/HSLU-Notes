>[!Definition]
>Die Kohäsion eines [[Modul|Moduls]] beschreibt das Ausmass der Kommunikation innerhalb des [[Modul|Moduls]]. Es beschreibt, wie "zusammenghörig" die Code-Teile innerhalb des Moduls sind.

**Ziel** ist es die Kohäsion zu maximieren.

**Beispiel**
![[Kopplung_Kohäsion.png]]
-> Geringe [[VSK/Modularisierung/Kopplung|Kopplung]], da fast keine interne Kommunikation vorhanden ist.

![[Kopplung_Kohäsion2.png]]
-> Hohe Kohäsion, da viele interne Kommunikation vorhanden ist.


## Arten
**Funktionale Kohäsion**
Alle Teile haben eine ineinandergreifende Beziehung zueiandner.
-> z.B. Funktionen innerhalb einer Klasse rufen sich gegenseitig auf und verwenden dieselben Properties.

**Logische Kohäsion**
Logisch, aber keine Funktionale Beziehung.
-> Mathematischen Funktionen welche zusammengehören, aber nicht Funktional ähnlich sind.


**Zufällige Kohäsion**
-> Einheiten sind zufällig im selben [[Modul]] gelandet.


## Messung
Die **funktionale Kohäsion** kann über das Mass *Lack of Cohesion in Methods* (LCOM) gemessen werden und gibt die Summe der nicht gemeinsam genutzten Methodensätze an, welche nicht auf geteilte Felder zugreifen.

![[LOCM.png]]