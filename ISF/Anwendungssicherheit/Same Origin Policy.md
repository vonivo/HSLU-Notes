Ein Webbrowser kann mehrere Webanwendungen parallel laufen lassen.
Die **Same-Origin-Policy** verhindert, dass eine parallel laufende Webanwendung uneingeschränkt:
- auf die Daten einer anderen Anwendung zugreiffen
- die Cookies einer anderen Anwendung leses oder mitschicken
- Requests auf die andere Anwendung absetzen
kann.

Die SOP gibt es z.B. für [[Cookies]], DOM-Access, HTML5Storrage, XMLHttpRequests.

## Cookies
Cookies haben eine **domain** und einen **path**.

**Setzen des Cookies:** Nur Domain-Suffix des URL-Hostname dürfen gesetzt werden (Aber ekeine Top-Level-Domain)

**Senden des Cookies:**
Cookies werden nur dann mitgeschickt, wenn die Cookie-Domain ein Domain-Suffix der URL-Domain und der Cookie-Path ein Refix des URL-Path ist.

**Beispiel**
Von login.site.com gesetzte Cookies:
- erlaubte Domains login.site.com; .site.com
- verbotenen Domains: user.site.com; othersite.com; .com

Ein Cookie mit der Domain .site.com
- wird geschickt nach login.site.com, other.site.com
- nicht geschickt nach user.othersite.com