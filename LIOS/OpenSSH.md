Secure Shell oder SSH bezeichnet ein kryptographisches Netzwerkprotokoll für den sicheren Betrieb von Netzwerkdiensten über ungesicherte Netzwerke.

Mit dem [[Prompt|Befehl]] `ssh` kann eine sichere Verbindung zu einem Remote-Server aufgebaut werden. Dabei kann man sich als bestimmten Benutzer authentifizieren und eine interaktive Shell nutzen.

**Beispiel**
```bash 
[labstudent@lios-1 ~]$ ssh -> lios-workstation-01 -l labstudent
```


Die Kommunikation wird dabei durch Verschlüsselung mittels Public Keys geschützt und läfut so ab:
1. Anmeldeversuch
2. Server sendet Public-Key an Client
3. Client verschlüsselt Daten mit Public-Key des Servers
4. Server kann Daten mit Privat-Key entschlüsseln.

## Wichtige Dateien
### `~/.ssh/known_hosts` und `/etc/ssh/ssh_known_hosts`
Diese Dateien speichern die Public-Keys der SSH-Server.
Jedes mal wenn ein Benutzer eine SSH-Verbindung zu einem neuen Server aufbaut, wird gefragt, ob dem Public-Key vertraut wird. Wird dies akzeptiert, wird der Schlüssel in der Datei `~/.ssh/known_hosts` gespeichert.

In der Datei `/etc/ssh/ssh_known_hosts` kann der Serveradministrator die Public-Keys der Server vorkonfigurieren.

### `/etc/ssh/ssh_config`
Diese Datei enthält alle SSH-Konfigurationen für den SSH-Client wie z.B. `StrictHostKeyChecking`.

## Schlüsselbasierte Authentifizierung
Die Authentifizierung bei SSH kann mit Passwort oder schlüsselbasiert erfolgen.
Das heisst, dass der Benutzer über einen eigenen Schlüssel authentifiziert wird.

Der Schlüssel kann mit `ssh-keygen` erzeugt werden. Danach wird der öffentliche Schlüssel mit `ssh-copy-id` auf den Server kopiert.

Falls mehrere SSH-Key existieren kann das Tool `ssh-agent` verwendet werden.


## Serverkonfiguration
Die Konfiguration des SSH-Server ist in der Datei `/etc/ssh/sshd_config` geregelt.

Hier kann beispielsweise die Passwortauthentifizierung deaktiviert werden und das root-login ausgeschaltet.