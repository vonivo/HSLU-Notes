>[!Definition]
>Zwinge Nutzende einer Komponente nicht in eine Abhängigkeit von Elementen, die er nicht benötigt!

- Ein Modul sollte als Ganzes sinnvoll nutzbar sein, und nicht nur Teile oder Bruchstücke davon.
	- Sind Einzelteile losgelöst sinnvoll nutzbar, sollte man sie auch in eigenständig wiederverwendbare Module ausgliedern

>[!Info]
>Besonders bei Libraries und Frameworks (Komponentenbibliotheken) sollte man mit den transitiven Abhängigkeiten sehr sorgsam umgeben!

=> CRP ist ein **exkludierendes** Prinzip (macht Dinge kleiner).