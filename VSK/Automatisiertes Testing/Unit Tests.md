---
aliases:
  - Komponenten Test
  - Modultest
  - Entwicklertest
---
Oft mit Komponenten-, Modul- und Entwicklungstest gleichgesetzt.

>[!Definition]
>**Unit Tests** testen einzelnen, in sich geschlossenen Units (meist Klassen).


**Ziele**:
- Schnell und einfach ausführbar.
- selbst validierend
- automatisierbar
- Test ohne Abhängigkeiten zu anderen Units.

**Positiv**
- Neue oder veränderte Komponenten können schnell getestet werden.
- Testen ist vollständig in die Implementation integriert.
- [[Test First]]-Ansatz möglich.
- Automatisiertes, übersichtliches Feedback/Reporting
- Messung von [[Code-Coverage]] möglich.

**Negativ**
- Für GUI etwas aufwändiger.
- Qualität im Auge behalten. (Qualität vor Quantität)
- In manchen Architekturen / Umgebungen schwierig umsetzbar.
