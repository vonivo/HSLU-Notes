Eine IP-Adresse ist eine [[Adressräume|globale Adresse]] welche vom [[IP|IP-Protokoll]] genutzt wird.

Die global vergebenen Adressen werden durch die Organisationen ICANN und IANA vergeben.

Ursprünglich war eine IP-Adresse eine 32-Bit lange eindeutige Kennung für jeden Rechner im Internet.

Bei einer IP-Adresse wird jedes Byte als Dezimalzahl geschrieben:
`100000000 00001110 00000001 00001101` -> `128.14.1.13`

# Kategorien
Die IP-Adressen wurden anfänglich in folgende Kategorien unterteilt:
![[IP-Kategorien.png]]

Zusätzlich wurden folgende speziellen Adressen definiert:
![[Special-IP-Adress.png]]

# Classless Inter Domain Routing
Mit der Zeit wuchsen die Organisationen, aber da die IP-Klasse festgelegt ist, musste eine weitere Aufteilung gemacht werden.
Dafür wurde intern neue Teilnetze erstellt (Subnets), welche aber nach aussen hin wie ein einheitliches Netz wirken.
![[Subnets.png]]

Durch das CIDR (Classless Inter Domain Routing) wird das Problem der Klassen-Aufteilung überwunden und die IP-Adresse wird in einen:
- Netz-Anteil
- Host-Anteil
unterteilt.

Jede Routing-Tabelle in jedem Router muss dafür um eine 32-Netzwerkmaske erweitert.

## Netzwerkmaske
Die Netzwerkmaske zeigt an, welcher Teil der IP-Adress zur Adressierung des Netzwerks dient und welcher zur Adressierung des Hosts.

**Beispiel:**
IP-Adresse: `192.168.1.15`
Netzwerkmaske: `255.255.255.0`

Durch eine Binäre [[Logische Verknüpfungen#AND|AND]]-Verknüpfung kann nun die Netzwerkadresse herausgefunden werden:
`11000000.10101000.00000001.00001111` -> `192.168.1.15`
`11111111.11111111.11111111.00000000` -> `255.255.255.0`

=> `11000000.10101000.00000001.00000000` -> `192.168.1.0` -> Netzwerkadresse

Die Netzwerkmase kann mit einem `/` und der Anzahl Bits welche von rechts eine `1`sind angeben werden: `192.168.1.15/24`


# Private IP-Adressen
Es wurden folgende Private-Adressen definiert:

| IP-Adresse            | CIDR-Notation  |
| --------------------- | -------------- |
| 10.x.x.x              | 10.0.0.0/8     |
| 172.16.x.x-172.31.x.x | 172.16.0.0/12  |
| 192.168.x.x           | 192.168.0.0/16 |
Spezialbereich
**169.254.0.0/16** -> APIPA (Automatic Private IP Adressing ohne [[DHCP]])
