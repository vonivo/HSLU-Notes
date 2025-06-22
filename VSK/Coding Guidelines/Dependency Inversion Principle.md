>[!Definition]
>High-Level-Klassen sollen nicht von Low-Level-Klassen abhängig sein, sondern allenfalls nur von Interfaces.

**Negative Beispiel**
![[DIP1.png]]

`Portfolio` (**High-Level**) ist direkt abhängig von `ZurichStockExchangeClient` (**Low-Level**).


**Besser**
![[DIP2.png]]
Diese Abhängigkeit wird hier mit dem [[Adapter]] aufeglöst. `Portfolio` ist nun nur noch von `StockExchange` abhängig.