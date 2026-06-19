>[!Definition]
>Eine [[Formale Grammatik|Grammatik]] $G$ liegt in Chomsky-Normalform vor, wenn alle Produktionen die Form $A\to \sigma$ oder $A\to BC$ besitzen mit $A,B,C \in V$

>[!Info]
>Syntaxbäume von CNF-Grammatiken sind [[Binäre Bäume]]


>[!Error]
>Jede [[Typ 2|kontextfreie Sprache]] lässt sich in Chomsky Normalform überführen.


**Beispiel einer Transformation:**
![[Pasted image 20260619125424.png]]
Die Schritte sind wie folgt:
1. **Neues Startsymbol einführen**: Falls das Startsymbol auf einer rechten Seite vorkommt: $S_{0}\to S$
2. **$\epsilon$-Produktionen entfernen**:
	1. Aus $S\to AB$ wird $S\to AB$ und $S\to A$
	2. Aus $S\to ABA$ wird $S\to ABA$ $S\to AA$
	3. Aus $S\to Bb$ wird $S\to Bb$ und $S\to b$
3. **Kettenproduktionen entfernen**: Reglen der Form $A \to B$ werden ersetzt:
	1. Aus $S\to A$ wird $S\to aA$ und $S\to aA$
4. **Nutzlose Symbole entfernen**
	- Nicht erreichbare Nichtterminale entfernen.
	- Nichtterminale entfernen, die kein Terminalwort erzeugen können.
5. **Terminale in langen Regeln ersetzen**: Regeln wie $A \to aBC$ dürfen Terminale nicht zusammen mit anderen Symbolen auftreten
	1. $S\to aA$ wird zu $S\to V_{a}A$ und $V_{a}\to a$
	2. $A\to aA$ wird zu $A\to V_{a}A$ und $V_{a}\to  a$
	3. $B\to Bb$ wird zu $B\to BV_{b}$ und $V_{b}\to b$
6. **Rechte Seiten auf Länge 2 reduzieren**: Rechte Seiten auf Länge 2 reduzieren.
	1. $S\to ABA$ wird zu $S\to S_{2}A$ und $S_{2}\to AB$
