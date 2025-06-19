>[!Definition]
>Ein Singleton gewährleistet, dass von einer Klasse nur genau ein Objekt erzeugt werden kann und stellt für diesen einen Zugriffspunkt bereit.
>
>- [[Creational-Patterns]]
>- [[Entwurfsmuster|Objektbasiert]]




![[Singleton.png]]
Die Singleton Klasse sollte noch mit `<<leaf>>` klassifiziert sein, da sie `final` ist.

**Eigenschaften**
- `private static` Feld der Klassen Instanz
- `private` [[Konstruktor]]
- `public static` Methode welche die Instanz zurückgibt.
- Klasse ist `final`

>[!Info]
>Der Singleton hat eine etwas schlechten Ruf, da er sehr schnell zu einer hohen [[Kopplung]] führen kann. (Späteres Austauschen schwierig)

**Empfehlung**
- Nie als globaler Zugriffspunkt nutzen.
- Zurückhaltend und gezielt einsetzen.
