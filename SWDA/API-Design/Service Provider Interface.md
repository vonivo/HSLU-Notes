---
aliases:
  - SPI
---
Das Service Provider Interface (SPI) ist eine spezielle Teilmenge oder Ergänzung zu einer [[API]].

Das SPI ist vor allem für Anbieter einer API-Implementation gedacht. Sie können ihre Implementation durch das SPI bei einer Factory der API zu registrieren oder verschieden Basiskonfiguration anzubieten.

SPI muss nicht zwingend Class-based sein, sondern kann auch eine Datei-Schnittstelle sein.

Die bewusste Abgrenzung durch ein explizites SPI verbessert die Gesamt-API und schützt sie diese massgeblich vor falscher Nutzung.