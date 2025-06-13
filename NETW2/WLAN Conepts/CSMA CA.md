WLAN sind im Halbduplex und könne während dem Senden nicht empfangen. Daher ist es für sie unmöglich eine Kollision zu detekieren.

WLAN nutzt Carrier Sense Multiple Access mit Collision Avoidance um festzustellen wie und wann Daten gesendet werden dürfen:
1. Auf dem Kanal hören und schauen ob niemand sendet.
2. Senden von einem "Ready to Send (RTS)" Nachricht zum AP, um dedizierten Zugang zu erhalten.
3. Erhalt von einem "Clear to Send CTS" vom [[AP]].
4. Abwarten eines zufälligen Timeouts, wenn kein CTS erhalten wurde.
5. Daten senden.
6. Alle Übertragungn Quitieren, wenn ein Client keine Quitierung erhält, nimmt er an, dass es eine Kollision gegeben hat.
