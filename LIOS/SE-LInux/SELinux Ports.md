Zusätzlich zu [[Dateikontext]] und Prozesstyp werden Netzwerkports in [[SE-Linux]] mit einem Kontext gekennzeichnet.

Beispielsweise enthält die SSH-Zielrichtlinie den Port 22/TCP mit der Portkontextbezeichnung `ssh_port_t`

# Befehle
## Portnummer auflisten
```bash
[user@host ~]$ grep gopher /etc/service
gopher      70/tcp
gopher      70/udp
```
## Portzuweisung
Um die SELinux-Portzuweisung aufzulisten wird folgender [[Prompt|Befehl]] verwendet:
```bash
[user@host ~]$ semanage port -l
```
Portzuweisung hinzufügen:
```bash
[user@host ~]$ semanage port -a -t port_label -p tcp|udp PORTNUMBER
```

Portzuweisung löschen:
```bash
[user@host ~]$ semanage port -d -t gopher_port_t -p tcp 71
```

