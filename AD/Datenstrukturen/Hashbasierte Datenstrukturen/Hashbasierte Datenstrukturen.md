>[!info]
>Man berechnet aufgrund von Daten eine Hashwert (z.B. int) welcher direkt auf den Speicherort der Daten innerhalb der [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]] zeigt. Somit wird ein Lesezugriff mit einer [[Komplexität]] von $O(1)$ möglich.

Um die Datenstruktur weiter zu optimieren, verwendet man zu Berechnung des Hashwertes nur Daten, welche den Identifikationsschlüssel repräsentieren. $\implies$ Weniger Daten ergibt eine schneller Berechnung des Hashwertes.


Der Hashwert selbst wird über die Funktion [[Equals & Hashcode#Hashcode|hashCode()]] erzeugt.


## Rahmenbedingungen
- Objekte welche in einer hashbasierten Datenstruktur verwendet werden, dürfen nicht verändert werden. (Hash-Wert wird verändert und die Daten können nicht mehr gefunden werden.) $\implies$ Vor Bearbeiten entfernen und nachher wieder hinzufügen.