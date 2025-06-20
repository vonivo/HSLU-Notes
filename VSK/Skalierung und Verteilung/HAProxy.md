>[!Definition]
>HAProxy ist ein Open-Source [[Reverse-Proxy]] welcher auch eine kommerzielle Version anbietet. HAProxy setzt dabei auf asynchrone I/O in Kombination mit mehreren [[Thread|Threads]].
>Die kommerzielle Version bietet Erweiterungen wie GeoIP-Routing und Traffic-Monitoring.

HAProxy ist ein einzelnes Binary und es gibt nur eine Konfigurations-Datei. `haproxy.conf`.


## Beispiel
**Start**
```sh
haproxy -V -f haproxy.conf
```

**Konfig**
```sh
global

defaults
	mode tcp               # Protkoll
	balance roundrobin     # roundrobin | leastconn | source | .... 
	timeout connect 5000ms # Timeout bei Verbindungsabufau
	timeout client 50000ms # Timeout Cliente-Inaktivität
	timeout server 50000ms # Timeout Server-Inaktivität

# Angabe des Listener-Interface für die Clients sowie des Ziel
# Backends
frontend http-in
	bind *:4000
	default_backend servers

# Liste aller Backend instanzen
backend servers
	server server1 127.0.0.1:8000 check
	server server2 127.0.0.1:8001 check
```
