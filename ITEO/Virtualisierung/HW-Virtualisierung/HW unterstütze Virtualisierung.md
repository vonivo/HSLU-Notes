Mit der HW unterstützen Virtualisierung wurde ein neuer CPU Modus eingeführt.
Er erlaubt die Ausführung von Befehlen unterhalb von Ring 0.

Dadurch Trappen privilegierte und sensitive Instruktionen automatisch und der VMM kann sie Handeln.

Das Gast OS sitzt nun im Ring 0 und alle Instruktionen werden an die CPU weitergeleitet. Die CPU überprüf, obb die Instruktion ausgeführt werden darf, wenn nicht wird ein VM-Exit ausgeführt, worauf der VMM anspricht und dasganzee handelt.