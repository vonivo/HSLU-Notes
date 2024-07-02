Das Sliding Window Protocoll ist ein Protokoll für die Flusskontrolle und **begrenzt die Anzahl Meldungen,** die hin und her geschickt werden. 
Dieses Protokoll wird bei [[TCP]] und HDLC (High Data Link Control)

![[SlidingWindow.png]]
Das Window definiert, wie viele Daten ohne eine Bestätigung (ACK) gesendet werden dürfen.

Ist das Fenster aufgebraucht stoppt der Sender, wird eine Bestätigung empfangen, wird das Fenster verschoben.