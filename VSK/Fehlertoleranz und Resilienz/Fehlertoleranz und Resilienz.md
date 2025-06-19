## Begriffe
- **Verfügbarkeit:** Beschreibt, ob ein System zum Zeitpunkt $t_{1}$ ob bereit ist Anfragen zu verarbeiten.
- **Hochverfügbarkeit:** Beschreibt ein System, welches zu grosser Wahrscheinlichkeit für Anfragen bereit ist (verfügbar).
- **Zuverlässigkeit:** Zeitintervall, innerhalb dessen ein System verfügbar ist.
- **Wartbarkeit:** Beschreibt die Zeitspanne, die benötigt wird, um ein **ausgefallenes** System wiederherzustellen.
- **Betriebssicherheit:** Gibt an, ob es zu katastrophalen Ausfällen kommen kann, wenn das System nicht verfügbar ist.
- **Fehler:** Ursache einer Funktionsstörung.
- **Fehlertoleranz:** Fähigkeit, dass ein System seine Dienste trotz Fehler bereitstellen kann.
- **Resilienz**: Widerstandsfähigkeit gegenüber schwerwiegenden Fehler-Ereignisse.


**Resilienz durch Redundanz**
- Schutz gegen Systemausfälle, da Systeme und Daten mehrfach vorhanden sind.
- Schutz vor byzantinischen Fehler (korrupte Daten). Erfoder ein [[Consensus-Protokoll]]

**Resilienz durch Wiederherstellbarkeit**
 - System kann nach Ausfall inert kurzer Zeit wieder hergestellt werden und läuft genau wie zuvor.


## Lokaler Cache: Server nicht erreichbar
Die Gegenstelle ist nicht erreichbar **vor** Aufbau der Verbindung:
![[lokaler_cache.png]]
**Erkennung:** Fehler beim Verbindungsaufbau.

**Massnahmen**
- Kein Betrieb möglich (z.B. Terminal-Server) -> Benutzer informieren.
- Reduzierter Betrieb möglich, falls Server nur Zusatzfunktionalität anbietet.
- Verwendung eines lokalen Caches.

**Vorgehen**
- **Lesen:** Informationen von früher gestellten Anfragen nutzen.
- **Schreiben**: Schreiboperationen in lokalen Cache ausführen und an den Server senden, sobald dieser wieder verfügbar ist.


## Verlorene Message (Request doer Reply)
![[lost_message.png]]
**Erkennung**
- Client startet Timer beim Absenden eines Request.
- Erhält der Client keine Antwort, bis der Timer abgelaufen ist, gilt die Message als Verloren.

**Massnahmen**
- Bei einer interaktiven Verbindung kann der Benutzer informiert werden.
- Falls sinnvoll, kann der Request nochmals gesendet werden.

## Server-Crash während Verarbeitung
![[Server_Crash.png]]
**Erkennung**
- **Client**: Stellt kein Unterschied zu verlorenen Messages fest.
- **Server**: Kann Log über Aktionen führen und beim Restart diese Aktionen abarbeiten. (Erforder i.d.R eine Datenbank)

**Massnahmen, falls Crash**
- vor Ausführung (== Verlorene Request), Client sendet Message erneut.
- während Ausführung: Konsistenz wiederherstellen.
- nach Ausfürhung: Reply senden.

## Client-Crash während Warten auf Antwort
![[client_crash.png]]
**Erkennung**
- Server erhält keine Verbindung zum Client

**Massnahmen**
- Falls der Client identifizierbar ist, kann die Reply gespeichert werden und später nochmals gesendet werden.
- Falls nicht identifizierbar, wird Antowrt verworfen.

>[!error]
>Problematisch, wenn Client Ressource wie z.B. bei NFS blockiert.


## Fehlende [[Konsitenz]] bei Duplikaterkennung
![[Duplikaterkennung.png]]
- Wie wird sichergestellt, dass Sequenznummer $N$ verarbeitet **und** markiert wird?

1. Anfrage wird verarbeitet und der Server crashed nacher -> Sequenznummer nicht markiert.
2. Sequenznummer wird markiert und der Server crashed nacher -> Aktion nicht ausgeführt.

==> Lösung: [[Transaktion]]