## Elementen
### Klasse
Ein Klasse besteht aus einem Namen, Attribute und Methoden und wird so modelliert:
![[Pasted image 20250102163310.png]]
#### Attribute
Attribute werden mit folgendem Ausdruck beschrieben:
![[Pasted image 20250102163511.png]]
**Sichtbarkeit**
- - private
- + public
- \# protected
- ~ package private

**Typ**
- Boolean
- Integer
- String
- Real

**Multiplizität**
- \[1..\*]
- \[0..1]

Statische Attribute werden Unterstrichen
Abgeleitete Attribute mit einem / als Präfix markiert.

#### Methoden
Methoden werden mit folgendem Ausdruck beschrieben:
![[Pasted image 20250102163839.png]]

**Parameterliste**
- Kommasepariert.

**Parameter**
- Bezeichner:Typ
- in (Default kann weggelassen werden)
- out
- inout

**Return-Type**
- Gleich Typen wie bei Attribute
- ohne Rückgabetyp => void

### Assoziation
Assoziation können mit einer Beschreibung und einer Leserichtung ergänzt werden.
#### Multiplizität
Die Multiplizität gibt Auskunft über wie viele Objekte miteinander assoziiert sind:
![[Pasted image 20250102164433.png]]
Möglich Werte sind:
- 1
- 1...\*
- 0...* oder *
- 0..1
- 3..*

#### Rollenbezeichner
Rollenbezeichner beschreiben die Bedeutung eines Objekts in einer Assoziation
![[Pasted image 20250102164556.png]]

#### Reflexive Assoziation
Als reflexiv bezeichnet man eine Assoziation, wenn eine Verbindung zwischen den
Objekten einer Klasse besteht.

Typen:
- "0..1 : \*" Baumstruktur
- "* : \*" Graphstruktur
![[Pasted image 20250102164741.png]]

#### Navigierbarkeit
Assoziationen können gerichtet sein, dass heisst, dass eine Klasse die andere "kennt" (sprich eine Referenz darauf besitzt.)
![[Pasted image 20250102164827.png]]

#### Typen
Hier ist die Übergeordnete Klasse immer *Class 1*
##### Assoziation
Repräsentiert die Beziehung zwischen verschiedenen Objekten:
![[Pasted image 20250102165008.png]]
##### Aggregation
- Beschreibt eine Zusammensetzung eines Objekts ("**besteht aus**" Beziehung)
![[Pasted image 20250102165054.png]]

##### Komposition
Ist eine Aggregation mit **existenzabhängigen Teilen**. Einzelteile haben ohne Aggregat keine Existenzberechtigung.
![[Pasted image 20250102165149.png]]

### Generalisierung
- Veralgemeiner: gemeinsame Attribute, Methoden und Beziehungen.
- Spezialisierung fügt Attribute hinzu.
- **IS-A**-Beziehung.
- Abstrakte Klassen mit "**\<\<abstract>>**" kennzeichnen:
- Abstrakte Methoden **Kursiv** schreiben.
![[Pasted image 20250102165426.png]]