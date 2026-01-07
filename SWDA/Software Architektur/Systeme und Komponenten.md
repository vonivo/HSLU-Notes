>[!Info]
>Softwaresysteme werden wenn möglich immer in einzelne Subsysteme (oder Teilsysteme zerlegt).
>- Zerlegung ist häufig mehrstufig hierarchisch.


## Subsysteme
Subsysteme haben eine gewisse Unabgängigkeit und interagieren über **wohl definierte Schnittstellen** miteinander.
- [[VSK/Modularisierung/Kopplung|Kopplung]] -> über möglichst lose Schnittstellen.
- [[VSK/Modularisierung/Kohäsion|Kohäsion]] -> mit Datenkapselung und Information Hiding

Durch diese hierarchische Strukturierung ergeben sich folgende Vorteile:
1. Präzisere Plan- und Schätzbarkeit
2. Unabängige Entwicklung
3. Einfaches Testing
4. Unabhängiges Deployment
5. Mögliche Wiederverwendbarkeit

## Komponenten
>[!Info]
>Eine Komponente ist eine softwaretechnische Einheit. (Achtung andere Definition als von [[Komponente]] im [[Komponentenmodell]]).

- Durch den Einsatz von Komponenten (und Klassen und Interfaces) kann ein System realisiert werden. 
- Ein System muss nicht zwingend Komponenten enthalten.
- Eine Komponente kann zur Realisation von mehreren Systemen verwendet werden (Wiederverwendung).