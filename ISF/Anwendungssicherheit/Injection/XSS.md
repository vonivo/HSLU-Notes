Ein Angreifer birngt eine legitimen Server dazu ein Script an den Browser zu senden. Dieses wird im Kontext des legitimen Servers ausgeführt. Es wird zwischen **stored** und **reflected** XSS unterschieden.

![[Pasted image 20250120205708.png]]
## Massnahmen
- Escaping aller unsicheren Daten (z.B. Benutzerdaten) bevor sie angezeigt werden.
- Cookie als HttpOnly setzen
- Heder-Felder seten (CSP, XSS-Protection)