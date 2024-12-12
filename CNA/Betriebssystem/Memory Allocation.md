Programme im [[Speicher]] können auf zwei Arten [[Speicher]] reservieren:

Abbildung a bezeichnet hier eine Art der Reservierung welche von Programmen genutzt werden die wachsende Datensegmente haben.

Abbildung b bezeichnet eine Art der Reservierung von Programmen welche sowohl wachsende Daten (Heap) als auch einen wachsenden [[Stack (Rechnerarchitektur)|Stack]] haben.

Füllt das Programm den ganzen Platz aus muss es im Memory gemoved werden zu einem Platz der gross genug ist, es wird geswaped auf den normalen [[Speicher]], oder das Programm wird beended (killed)
![[Programme im Speicher.png]]

# Dynamische Memory Allocation
Memory Allocation ändert sich laufend während [[Prozesse]] ins Memory geladen werden und das Memory wieder verlassen. 

Die folgende Illustration beschreibt diesen Vorgang: 
![[Pasted image 20240526151126.png]]

Das Memory wird gefüllt mit den Prozessen A,B und C. Diese werden entweder frisch erstellt oder von persistentem [[Speicher]] hineingeswapped ((a),(b),(c)). A verlässt das Memory und wird durch D ersetzt ((d),(e)). B verlässt nun ebenfalls den [[Speicher]] und der freie Platz zwischen D und C wird wieder für A genutzt ((f),(g)). Hierbei ist zu beachten das A nicht wieder am selben Platz ist wie vorher, also die Speicheradressen sich verändert haben. 

Um freien [[Speicher]] im Memory optimal nutzen zu können verwendet man die [[Garbage Collection]] oder die [[Defragmentierung]].