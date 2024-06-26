RedHat Enterprise [[Linux]] enthält das Tool `systemd-tmpfiles` und wird beim Systemstart als eines der ersten Programme von [[Systemd]] aufgerufen.
Der Service führt das `systemd-tmpfiles-Befehlsoption --create --remove` aus, die Anweisungen aus der Konfigurationsdatei `/usr/lib/tmpfiles.d/*.conf`,`/run/tmpfiles.d/*.conf` und `/etc/tmpfiles.d/*.conf` lesen.

In diese Konfigurationsdateien werden Dateien und Verzeichnisse aufgeführt, welche von Service gelöscht, erstellt oder mit Berechtigungen gesichert werden.