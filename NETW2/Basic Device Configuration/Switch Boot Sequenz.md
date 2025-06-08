Wenn ein Cisco Switch bootet druchläuft er folgende Schritte:
1. Power-On-Self-Tests POST aus ROM laden und ausführen.
2. Boot-Loader-Software aus ROM laden.
3. Low-Levle CPU initizalisierung duchr Boot-Loader.
4. Inizialisieren von Flash-File-System.
5. Boot-Loader lokalisiert und lädt IOS-Operation-System.

Der Switch versucht immer automatisch zu Booten mit den Informationen aus der BOOT-Env-Variable. Wenn diese nicht spezifiziert ist, wird das erste Executable geladen.

Nach dem Starten des IOS werden die Konfiguration der startup-config (im Flashspeicher unter `config.text`) geladen.

**Setzen der Boot-Env-Variable**
```sh
boot system flash:c2960-lanbasek9-mz.150-2.SE/c2960-lanbasek9-mz.150-2.SE.bin
```

