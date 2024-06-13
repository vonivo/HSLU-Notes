Ein regulärer Ausdruck (Regular Expression oder RegEx) ist ein Ausdruck welcher eine [[Formale Sprache|formale Sprache]] vom [[Typ 3]] darstellen kann.

Reguläre Ausdrücke werden von links nach rechts und prioritär durchlaufen.

| Operation     | Priorität (höchste 1) | Regulärer Ausdruck | Wörter                           |
| ------------- | --------------------- | ------------------ | -------------------------------- |
| Alternative   | 4                     | aa\|bb\|abba       | aa<br>bb<br>abba                 |
| Konkatenation | 3                     | aabaab             | aabaab                           |
| Wiederholung  | 2                     | ab*a               | aa<br>abbbbbba                   |
| Klammern      | 1                     | a(a\|b)\*aaf       | aaaf<br>aaaaf<br>abaaf<br>abbaaf |
