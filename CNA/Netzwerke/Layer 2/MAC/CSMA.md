Carrier Sense Multiple Access (CMSA) ist ein [[MAC]] protokoll.
CSM läuft so ab:
1. Sender hört den Datenverkehr auf der Leitung ab (= carrier sense)
2. Sender wartet bis der Kanal frei ist.
3. Soblad der Kanal frei ist, darf gesendet werden.
4. Falls mehrere Sender (fast) gleichzeitig anfagen zu senden: Kollision -> Wiederholung anch zufälliert Zeitpsanne.

# CSMA/CA
Carrier Sense Multiple Access / Collision Avoidance funktioniert so:
- Kollisionsvermeidung durch zufällige Wartezeit nach Erkennung eines freien Kanals, Reservation

=> Wlan 802.11-DCF verwendet dies

# CSMA / CD
Carrier Sense Multiple Access / Collision Avoidance funktioniert so:
- sobald eine Kollision erkannt wird, wird die Übertragung abgebrochen

=> Ehternet verwendet das.