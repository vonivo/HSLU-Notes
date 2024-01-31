Wenn bei Value-Types die [[Equals & Hashcode#equals|Equals-Methode]] überschreiben wird, muss unbedingt der [[Equals & Hashcode#equals Contract|Vertrag]] eingehalten werden. Ansonsten kann das Programm sich unbeabsichtigt verhalten oder sogar ganz crashen. (Die Fehlersuche wird dann extrem schwierig)

>[!info]
>Wenn der [[Equals & Hashcode#equals Contract|Equals-Vertrag]] missachtet wird, kann man nie vorhersagen wie anderer Objekte, welche mit dem Objekt interagierer, regagieren werden.
>

>[!warning]
>Bei `double` und `float` sollte `Float.compare(...)` benutzt werden. Wenn `Float.equals()` verwendet wird, entsteht ein unnötiges Boxing, was die Performance verschlechtert.


## Beispiele von Verletzungen
- `java.sql.TimeStamp` erweitert `java.util.Date` und fügt das [[Attribut]] `nanoseconds` hinzu. Damit verletzt dies den [[Equals & Hashcode#equals Contract|Equals-Vertrag]] und kann ungewünschtes Verhalten hervorrufen, wenn diese beiden Typen in z. B. einem Set gemischt werden.
- `java.net.URL` löst bei `equals` die IP auf, wenn jedoch kein Netz zur Verfügung steht, ist dies darum **inkonsistent**.

