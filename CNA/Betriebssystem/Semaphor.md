Ein Semaphor wird verwendet um Konflikte bei [[Interprocess Communication]] zu vermeiden. 
Es besteht aus einer Integer-Variable auf die über 2 Operationen zugegriffen werden kann: 

- Wait, Acquire, P(s), Down Operation 
	- Zählt das Semaphor runter (sofern es grösser als null ist)
	- Ist das Semaphor null wird der [[Prozesse|Prozess]] schlafen gelegt, da die Ressource zur Zeit besetzt ist
- Release, V(s), Up Operation
	- Zählt das Semaphor um eines hoch
	- Sobald das Semaphor hochzählt wird ein schlafender, wartender [[Prozesse|Prozess]] aufgeweckt → Dieser Acquired wiederum ein Semaphor

**Pro kritischem Abschnitt wird ein Semaphor benötigt**

