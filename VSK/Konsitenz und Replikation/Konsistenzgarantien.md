>[!Definition]
>Eine **Konsistenzgarantien** ist eine Anforderung an verteilte Applikationen, welche die notwendige Art der [[Konsitenz]] bestimmt.

Typische Konsistenzgarantien:
- **[[Sequential Consistency]]**: Die Sequenz der Operationen eines Gesamtsystems $S$ ist für alle Teilsysteme von $S$ die gleiche und passt in die Gesamtordnung.
- **[[Eventual Consistency]]**: Modifikationen werden erst mit einer gewissen Verzögerung sichtbar.
