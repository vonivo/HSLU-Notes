Eine Bridge ist ein intelligentes Gerät, welches gleich- und verschiedenartige [[Netzwerke]] verbinden kann. Die Bridge agiert dabei auf dem [[Data-Link-Layer]].

![[Bridge.png]]
Die Bridge liest alle [[Dataframes]] der angeschlossenen Netzwerke mit und erstellt daraus eine Tabelle, in welchem Netzwerk sich welche [[Adressräume#MAC-Adressen|MAC-Adresse]] befindet.

Befindet sich die Zieladresse auf der einen Seite der Bridge, wird das Paket nicht weitergeleitet, befindet sich die Zieladress jedoch im anderen Teil wird das Paket weitergeleitet.
=> Reduziert Nutzlast und Kollisionen.

Die Bridge kann dabei selbst jedoch **nicht adressiert werden**.

# Transparente Bridge
Eine transparente Bridge verbindet zwei lokale [[Netzwerke]] mit **demselben Data-Link-Protokoll** ([[IEEE-802]])

# Übersetzende Bridge
Eine übersetzende Bridge verbinden zwei unterschiedliche lokale Netzwerke mit **verschiedenen Data-Link-Protokollen**. (z.B. Ethernet -- Tokenring).

Um dies zu bewerkstelligen, besitzt die Bridge meist auch unterschiedliche Anschlüsse und muss Geschwindigkeitsanpassungen und Frameanpassungen vornehmen.
![[TranslatingBridge.png]]
# Virtuelle Bridge
Eine virtuelle Bridge erweiterte reelle Netzwerkarten um virtuelle Netzwerkarten, die dann von einem virtualisierten OS benutzt werden können.

# Remote-Bridge
Eine Remote-Bridge ist eine Bridge, die weit entfernte LANs über ein WAN verbindet. 
Die Datenübertragung im WAN erfolgt mittels WAN-Protokollen und es sind Übersetzungsoperationen nötig.

Dadurch "tunneln" LAN-Frames durch das WAN und die Netzwerke werden verbunden.


