Statische Routen können für IPv4 und IPv6 vergeben werden. Dabei exisitieren verschiednen Typen:
- Standard static route
- Default static route
- Floating static route
- Summary static route

Statische Routen werden über `ip route` und `ipv6 route` global konfiguriert.


## Next Hop
Wenn eine statische Route konfiguriert wird, muss der nächste Hop angegeben werden. Dies kann über eine **IP-Adresse**, **Egress-Interface** oder beides gemacht werden.

- **Next-hop route**- Nur die IP-Adresse ist spezifiziert.
- **Directly connected static route**: Nur das Egress-Interface ist spezifiziert.
- **Fully specified static route**: Beides ist spezifiziert.

## Konfiguration
### Standard Static Route
```
R1(config)# ip route <network-addr> <subnet> {ip-addr | <exit-intf> [ip-addr]} [distance]
# IPv6
R1(config)# ipv6 route <prefix/length> {ipv6-add | exit-itf [ipv6-addr]} [distance]
```

**Next Hop static Route**
```
R1(config)# ip route 172.16.1.0 255.255.255.0 172.16.2.2
# IPv6
R1(config)# ipv6 unicast-routing
R1(config)# ipv6 route 2001:db8:acad:1::/64 2001:db8:acad:2::2/64
```

**Directly connected static route**
```
R1(config)# ip route 172.16.1.0 255.255.255.0 s0/1/0
# IPv6
R1(config)# ipv6 route 2001:db8:acad:1::/64 s0/1/0
```

**Fully specified static route**

```
R1(config)# ip route 172.16.1.0 255.255.255.0 g0/0/1 172.16.2.2
# IPv6
R1(config)# ipv6 route 2001:db8:acad:1::/64 s0/1/1 fe80::2
```

>[!Error]
>Wenn eine Link-Local Adresse genutzt wird, muss eine **Fully specified static route** verwendet werden.


### Default Static Routes
Eine Default-Static Route ist eine Route wleche alle Pakete matcht.
Diese Default Route wird als "Gateway of last Resort" genutzt, beispielsweise zum ISP.

```
R1(config)# ip route 0.0.0.0 0.0.0.0 172.16.2.2
R1(config)# ipv6 route ::/0 2001:db8:acad:2::2
```

### Floating Static Route
Floating Static Route sind Routes welche einen Backup-Pfad zu einer Primären-Statischen-Route oder zu Dynamischen-Statischen-Routen bereitstellt.

Um dies zu erreichen, wird eine höhere [[Routing-Tabelle|administrative Distanz]] gesetzt.

```
R1(config)# ip route 0.0.0.0 0.0.0.0 172.16.2.2
R1(config)# ip route 0.0.0.0 0.0.0.0 10.10.10.2 5


R1(config)# ipv6 route ::/0 2001:db8:acad:2::2
R1(config)# ipv6 route ::/0 2001:db8:feed:10::2 5
```

### Static Host Route
Eine Host Route ist eine IPv4 Adresse mit einer 32-Subnetzmaske, oder eine IPv6 Adresse mit 128-Bit Maske.

Es gibt 3 Arten diese hinzuzufügen:
- Automatische Erstellung, wenn eine IP-Adresse konfiguriert wird.
- Konfiguriert als statische Route.
- Automatisch erlernt durch andere Methoden

```
R1(config)# ip route 209.165.200.238 255.255.255.255 198.51.100.2


R1(config)# ipv6 route 2001:db8:acad:2::238/128 2001:db8:acad:1::2
```