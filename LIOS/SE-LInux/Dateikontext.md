Druch [[SE-Linux]] wird jeder Datei ein Dateikontext zugewiesen, welcher so aussieht:
`unconfined_u:object_r:httpd_sys_content_t:s0 /var/www/html/file2`

Spalten:
1. SELinux User
2. Role
3. Type
4. Level
5. File

Viele [[Prompt|Befehle]] verwende die Option `-Z` welche den SELinux-Kontext anzeigt oder festlegt.

# Befehle
## Dateikontexte anzeigen
```bash
[user@host ~]$ semanange fcontext -l
```

## Dateikontext temporär ändern
```bash
[user@host ~]$ chcon system_u:object_r:httpd_config_t:s0 httpd.conf
```
## Dateikontext permanent ändern
Um den Dateikontext permantent zu ändern muss ein Eintrag im `semanage fcontext`gemacht werden, dies ist ein Mapping von Pfäden mit [[Regex]] und dem Kontext.
```bash
[user@host ~]$ semanange fcontext -a -t http_sys_content_t "/Test(/.*)?"
```
## Dateikontext wieder herstellen
```bash
[user@host ~]$ restorecon -Rv /Test
```