**Can pipes bi bidirectional in a pipeline architecture?**
Ja, sie könnten es sein. Es sollte aber definitiv vermieden werden. Da Pipes sollten nur unidirektional sein, damit eine klare Separation of Concerns gemacht werden kann.

**Name the four typs of filters and their purpose.**
1. Producer -> Startpunkt der Pipeline. Nimmt externe Daten und fütter diese in die Pipeline.
2. Transformer -> Transfomiert Daten, aggregiert, erweiter oder entfernt Daten.
3. Tester -> Konditionaler Filter welcher entscheidet ob und wo die Pipeline fortgesetzt wird.
4. Consumer -> Ende der Pipeline, speichert Daten in der Datenbank oder kann diese auch visualisieren, etc.

**Can a filter send data out thorugh multiple pipes?**
Ja, das ist möglich und zwar kann das mit einem Tester-Filter gemacht werden, welcher dann mehrere Ausgänge hat und entsprechend weiterleitet.

**Explain why the pipeline architecture is well suited for cloud based environments**
Diese Architektur kann gut in die Cloud transportiert werden. Einerseits z.B. alles gut als monolitscher Container deployed werden oder aber auch einzelne Filter einzeln um es so zu einer verteilten Applikation zu machen, zustzlich können auch z.B. Amazon Step-Funktions genutzt werden.

**Is the pipeline architecture style technically partitioned or domain partitioned?**
Technischn

**In what wa does the pipeline architecture support modularity.**
Modularity wird durch diesen Style sehr gut unterstützt, da ein Filer als eine Architektonische Komponente gesehen wird und so die Applikation sehr modular gebaut wird.

