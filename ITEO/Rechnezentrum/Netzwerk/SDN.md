Software-Defined-Network will dem statischen Ansatz von herkömmliche Netzwerken entfliehen. 
SDN will dem komplexen Management der herkömmlichen Geräte (pro Hersteller, andere Software (teil pro Gerät, andere Software)) Abhilfe schaffen.

Im Großen und Ganzen sind alle Netzwerkkomponenten ähnlich aufgebaut, sie besitzen einen Hardware-Data-Pfad und einen Software-Control-Teil.
![[Pasted image 20250104115323.png]]
Im Grunde wird bei jedem Netzwerkgerät an einem Port ein Paket empfangen regelbasiert an einen weiteren Port weitergeleitet.

Dies macht sich SDN zunutze.

## Grundstruktur
Die HW-Data-Path-Schicht wird nun als einfach Forwarders definiert, welche einfach Pakete verwerfen oder weiterleiten.

Die Software-Control-Schicht wird zur Controller-Schicht und ist nun dafür zuständig, die Benötigten Protokolle auf die Forwarder zu verteilen, damit diese die Pakete weiterleiten könne.

Als Letztes kommt noch eine Application-Schicht hinzu, welche die Verwaltung des Controllers erlaubt.
![[Pasted image 20250104115900.png]]=> Verwaltung des Netzwerks zentral über einen Serverdienst

Eigenschaften:
- Eigenschaften des [[Netzwerk]] können dynamisch angepasst werden.
- Entkopplung von Data Plane und Control-Plane
- Anforderungen von Protokollen (QS) und Applikationen könne dynamisch angepasst werden.
- Höhere Bandbreiten können erreicht werden

### Flowspace
Der Hader eines IP-Pakets bestimmt die Aktionen des Forwarders.
Es gibt wenige Möglichkeiten
- Plumbing: Paket weiterleiten
- Control: Paket an Controller senden
- Routing between Flow-space: Header umschreiben.
- Bandwith isolation

Jeder Forwarder hat eine sogeannten Flow-Tabel mit regeln, wie ein Paket zu handhaben ist.

Ein Eintrag in der Flow-Tabel sieht so aus:
![[Pasted image 20250104123147.png]]
**Beispiele**
![[Pasted image 20250104123238.png]]