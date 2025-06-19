>[!Definition]
>Ein Adapter passt die Schnittstelle einer vorhandenen Klasse, an die von den Nutzenden erwartete Schnittstelle an.
>- [[Structural-Patterns]]
>- [[Entwurfsmuster|Klassen- oder Objektbasiert]]

![[Adapter.png]]**Motivation**
- Einfachere Wiederverwendung von existierenden Klassen oder Komponenten der Schnittstelle aber unpassend ist.
- Ein möglichst allgemeine Schnittstelle zu implementieren und die Adapter dann anzupassen.
- Entkopplung von Drittschnittstelle mit eigenem System.

**Eigenschaften**
- Interface (z.B. `LogPersistor`)
	- Ist die gewünschte Zielschnittstelle.
	- Kann eine abstrakte Klasse oder ein Interface sien.
- Adapter: (z.B. `StringPersistorAdatper`)
	- Verwendet die adatpierte Klasse / Objekt
	- Spezialisiert oder implementiert die Zielschnittstelle.
- Adaptierte Klasse (z.B. `StringPersistor`)
	- Adaptierte Klasse, deren Schnittstelle adaptiert werden soll.
