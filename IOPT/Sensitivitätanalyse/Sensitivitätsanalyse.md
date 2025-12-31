>[!Definition]
>Mit der Sensitivitätsanalyse lässt sich analysieren
>- wie robust eine optimale Lösung
>- wie sich die Lösung bei verändern der Input-Parameter verändert.
>Somit können mehrere Szenarien optimiert werden.

Wichtige Informationen aus der Dualiatätstheorie sind daher:
- Schattenpreise
- Reduzierte Kosten
- Gültigkeitsbereiche

Der Sensitivitäsreport kann bei fast jeder Software generiert werden:
Beispiel in Lindo:
![[Schattenpreise.png]]
![[Schattenpreise2.png]]
Wie im Screenshot zu sehen (grün) gibt es zu jeder Bedingung einen **Schlupf** und einen **Schattenpreis** und einen **Gültigkeitsbereich**.

Zu jeder Variable existieren die **reduzierten Kosten** und einen **Gültigkeitsbereich**.

- **Slack Or Surplus**: Schlupfs zeigt den Schlupf einer Bedingungen an (z.B. wurde 5 Motoren nicht verwendet)
- **Dualprice**: Schattenpreis.
  Zeigt an, wie sich die Optimallösung verändert, wenn die RHS einer Bedingung um eine Einheit erhöht wird. **Ist aber an einen Gültigkeitsbereich gekoppelt.**
- **Reduced Kost**: Betrag, um welchen die Zielfunktionskoeffizienten erhöht (bzw. vermindert) werden muss, damit die Variable positiv werden kann. 
  **Oder** Rate mit welcher der Zielfunktionswert ändert, wenn die Variable von 0 auf einen kleinen positiven Wert forciert wird. **Auch an einen Gültigkeitsbereich gekoppelt** 