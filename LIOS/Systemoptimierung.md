Ein System kann optimiert werden, indem Geräteeinstellungen basierend auf verschiedenen Anwendungsfälle abgestimmt wird.

Der [[Daemon]] `tuned` wendet Tuning-Anpassungen sowohl statisch als auch dynamisch an. Dabei werden Tuning-Profile verwendet, die bestimmte Workload-Anforderungen berücksichtigen.
- **Statisch** -> Festlegung der **allgemeinen Leistungserwartungen**, ohne dies anzupassen, wenn sich die Aktivitätsebenen ändern.
- **Dynamisch** -> Systemaktivität wird überwacht und Einstellungen entsprechende angepasst.

# Monitoring
In Redhat gibt es drei verschieden Monitoring-Plug-Ins:
- disk -> Überwacht die Festplatte basierend auf Anzahl E/A-Vorgänge für jedes Gerät
- net -> Überwacht die Netzwerkauslastung basierend auf der Anzhal pro Netzwerkkarte übertragenen Pakete
- load -> Überwacht die CPU-Auslastung für jede CPU

# Tuning
Auch beim Tuning existieren drei Plug-Ins:
- disk -> Legt verschiedene Festplattenparameter fest. (z.B. Festplatten Scheduler, Spin-Down Zeitlimit, Energieverwaltung)
- net -> Konfiguriert Schnittstellengeschwindigkeit und die Wake-on-LAN-Funktion (WoL)
- cpu -> Legt verschiedene CPU-Parameter fest (z.B. CPU-Regler oder Latenz)

=> Dynamisches Tuning standardmässig deaktiviert. Variable `dynamic_tuning` in `/etc/tuned/tuned-main.conf`


# `tuned` Dienstprogramm
`tuned` umfasst Profile für folgende Kategorien:
- Sparen von Energie
- Steigerung der Leistung

Tuned speicher die Tuning-Profile in dem Verzeichnis `/usr/lib/tuned`und `/etc/tuned/` 