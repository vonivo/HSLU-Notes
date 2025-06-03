Bei SQL-Injektions wird bei einfacher Konkatenation von Strings zu Querys die Escape zeichen von SQL ausgenutzt um so ein böses Query zu generieren:
![[Pasted image 20250120205450.png]]
## Massnahmen
- Prepared-Statements verwenden
- Whitelisting der Inputs
- Sanitizing der Inputs
- Rechte des technischen Benutzers auf der DB einschränken.
- Verwenden eines sicheren APIs
