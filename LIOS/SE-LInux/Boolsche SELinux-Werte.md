Die Richtlinien von [[SE-Linux]] werden vom Anwendungsentwickler gesetzt und bestimmt. Ein Entwickler kann daher auch ein optionales Verhalten für spezifische Situationen implementiert. Diese werden **boolsche SELinux Werte** genannt.

# Werte Auflisten
```bash
[user@host ~]$ getsebool -a
abrt_anon_write --> off
abrt_handle_evnet --> off
abrt_upload_watch_anon_write --> on
```

# Werte ändern
```bash
[user@host ~]$ setsebool http_enable_homeidrs on
```
