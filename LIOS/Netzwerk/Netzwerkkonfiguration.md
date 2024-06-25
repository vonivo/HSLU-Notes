Um unter [[Linux]] [[Netzwerkschnittstelle|Netzwerkschnittstellen]] zu konfigurieren existieren verschieden Möglichkeiten:
- `iproute2`-Kommando
- `nmcli`
- GNOME `control-center` Applikation
- Konfigurationsdatei in `/etc/sysconfig/network-scripts/ifcfg-*` 

# `iproute2`
Das Programm `iproute2` stellt verschieden Befehle zur Verfügung, um Konfigurationen der Netzwerkschnittstelle aufzulisten oder zu bearbeiten.
Die Änderungen welche mit `iproute2` gemacht werden, sind jedoch volatil und nach einem Reboot nicht mehr verfügbar.

Beispiel:
`ip link`-> Listet alle Schnittstellen auf
`ip addr` -> Listet alle Schnittstellenkonfigurationen auf

# `nmcli`
Das Programm von Read Hat Network-Manager-Command-Line-Interface wird genutzt, um die Schnittstellenkonfiguration durchzuführen. Dabei wird vom Programm die Dateien unter `/etc/sysconfig/network-scripts/ifcfg-*` bearbeitet.
Änderung, welche von diesem Tool gemacht werden, sind persistent.

Beispiele:
`nmcli dev status`
`nmcli dev show ens256`
`nmcli con show --active`
`nmcli con show "System ens192"`
`nmcli con add con-name ens26-con type ethernet ifname ens256 ipv4.address 192.168.0.5/24 ipv4.gateway 192.168.0.254`
`nmcli con mod "ens26-con" ipv4.dns 4.2.2.4 connection.autoconnect no`

## Control-Center
Dieses Tool ist in den Einstellungen von GNOME zu finden und ist ein GUI-Tool. Dabei wird vom Programm die Dateien unter `/etc/sysconfig/network-scripts/ifcfg-*` bearbeitet. Änderungen, welche von diesem Tool gemacht werden, sind persistent.

# Konfigurationsdatei
Das Verzeichnis `/etc/NetworkManager/system-connections/` speichert persistente Profile, welche der Benutzer erstellt hat. Der Network Manager kopiert diese Profile automatisch in das Verzeichnis `/etc/sysconfig/network-scripts/ifcfg-*`

Das Verzeichnis `/run/NetworkManager/system-connections/` speichert temporäre Profile, welche automatisch wieder entfernt werden.

Im Verzeichnis `/usr/lib/NetworkManager/system-connections/` werden die unveränderlichen Standardprofile gespeichert.

Wenn eine Datei unter `/etc/NetworkManager/system-connections/` geändert wurde, muss der [[Prompt|Befehl]] `nmcli con reload` und `nmcli con up "name"` ausgeführt werden.