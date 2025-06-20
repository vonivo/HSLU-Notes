Die Ziele der Envirnomen Konfiguration sind:
- Pro Komponente existiert **nur ein Buildartefakt**. (Selber Build für Development-, Test- und Produktive-Systeme)
- **Umgebungen** sind zur Laufzeit **identifizierbar**.
- Umgebungskonfigurationen sind **dokumentiert** und **identifizierbar**.
- Umgebungskonfigurationen sind **versioniert**.
- **Reproduzierbare** Entwicklungs-, Test-, QA-, und Produktionsumgebungen.

![[Umgebungskonfiguration.png]]- 
- Daten der Umgebung sind immer spezifisch
- Konfigurationen sind ebenfalls spezifisch, aber versioniert

**Entkopplung von Code und Umgebungsinformationen**
Umgebungsinformationen dürfen nicht hardcodiert werden, da sich ansonsten der Build für die verschiedenen Systeme unterscheidet.
Daher werden sie entweder über ein **Konfigurationsfile** konfiguriert oder über **Umgebungsvariable injiziert**.


**Beispiel 1: Umgebungsvariable durch Skripting**
Wird angewendet wenn keine Containervirtualisierung zur Verfügung steht
```sh
## set_env.sh ##
export MAIL_HOST=testmail.example.com
export MAIL_PORT=443
export PAYMENT_HOST=testpay.service.com
export PAYMENT_PORT=443
export BACKEND_HOST=test1.example.com
export BACKEND_PORT=3003
export DATABASE_HOST=test1.example.com
export DATABASE_PORT=2031

## start_test.sh ##
~$ source ./set_test_env.sh
~$ java –jar mybackend.jar \
      –port BACKEND_PORT \
      -mailHost=${MAIL_HOST} \
      –mailPort ${MAIL_PORT} \
      -dbHost=${DATABASE_HOST} \
      -dbPort=${DATABASE_PORT} \
      -payHost=${PAYMENT_HOST} \
      -payPort=${PAYMENT_PORT
```


**Beispiel 2: Umgebungsvariable durch Docker-Compose**
```yaml
services:
  web:
    image: myserver
    ports:
      - "433:5000"
    environment:
      LISTEN_PORT: 5000
      REDIS_HOST: redis
      REDIS_PORT: "6379"
      EMAIL: smtp.test.ch
    volumes:
      - logvolume01:/var/log
    links:
      - redis
  redis:
    image: redis
    envirnoment:
      LISTEN_PORT: 6379
```
Hier werden alle Umgebungsvariablen unter dem Punkt 'environment' gesetzt.
Pro Umgebung gibt es ein docker-compose.yaml File.

Die einzelnen Services lesen die Variablen dann aus:
```python
import time
import os
import redis
from flask import Flask

app = redis.Redis(
  host=os.environ["REDIS_HOST"],
  port=os.environ["REDIS_PORT"]
)
```

Weiter Tools zur Umgebungskonfiguration:
- Docker Swarm / Kubernetes / Open Shift: Transpartente Verteilung auf mehreren Systemen
  - Verschlüsselung / Lastverteilung / Redundanz
  - Separate Tools (Trafik / haproxy / etc.) sind meistens mächtiger
  - Redundanz muss von der Datenbank unterstützt werden
- Helm: "Package Manager" für Kubernetes


**Konfiguration muss versioniert werden können.**
- Ideal ist Infrastructure as Code (z.B. Docker-Compose)