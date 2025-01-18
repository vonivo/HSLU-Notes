Ein **namespace** abstrahiert eine globale Systemressource (bsp. Benutzergruppen, Benutzer usw.) in der Art, dass der zum Namespace gehörende Prozess denkt er besitzt die Ressource alleine.

Änderungen an dieser globalen Ressource sind nur sichtbar für die Mitglieder im gleichen Namensraum. Für andere Prozesse sind sie nicht sichtbar.

**Linux Namespaces**
- **Mount-Namespace**: isolieren die FS Mountpoints wie sie von Prozseen gesehen werden.
- **UTS-Namespace** isolieren 2 System-IDs. Node Name und Domainname. Das erlaubt jedem Container, seinen eigenen Hostname zu tragen.
- **IPC-Namespace**: isolierten gewisse Ressourcen fürInter-Prozess-Kommunikation
- **PID-Namepsace:** isolieren den Prozess-ID-Nummernraumm. So können Container alle einen Prozess mit PD 1 haben.
- **Network Namespace**: isoliert die Systemressourcen welche in Verbindung mit dem Netzwerk stehen. So kann jeder Namesraum sein eigenes Netzwerk-Interface haben.
- **User-Namespaces**: isolieren den User- und Gruppen-ID Nummernraum. So kann ein Prozess innerhalb des Namespace volle Root-Rechte außerhalb jedoch keine Privilegien habe.