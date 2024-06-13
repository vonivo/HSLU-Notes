Die Backus-Naur-Form (BNF) oder die erweiterte Backus-Naur-Form (EBNF) ist eine Form der Darstellung der [[Formale Grammatik|Grammatik]] einer [[Formale Sprache|formalen Sprache]] des [[Typ 2]] oder höher.

## Backus-Naur-Form
- Nichttermianlsyombole werden mit $<\dots>$ gekennzeichnet
- Terminalsymbole verwendet man 1:1
- Aneinanderreihung bindet stärker als Alternativen.
- Metasymbole:
	- $::=$ -> Ist definiert
	- $|$ -> Trennt alternativen

### Beispiel
$<GanzeZahl>::= <Zahl>|<Vorzeichen><Zahl>$
$<Zahl>::= <Ziffer>|<Ziffer><Zahl>$
$<Vozeichen>::= +|-$
$<Ziffer>::=0|1|2|3|4|5|6|7|8|9$



## Erweiterte Backus-Naur-From
Zusätzlich zur BNF wurde folgende Metasymbole definiert:
- $(\dots)$ -> Gruppierung, Inhalte zusammen betrachten.
- $[\dots]$  -> Option, Inhalt steht genau 0 oder 1 Mal.
- $\{\dots\}$ -> Wiederholung, Inhalt steht beliebig oft (auch 0-mal)

### Beispiel
$<GanzeZahl>::=[+|-]<Ziffer>\{<Ziffer>\}$
$<Ziffer>::=0|1|2|3|4|5|6|7|8|9$

