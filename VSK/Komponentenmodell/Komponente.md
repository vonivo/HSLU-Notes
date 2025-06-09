>[!Definition]
>Eine Software-Komponente ist ein Software-Element, das zu einem **bestimmten Komponentenmodell** passt und entsprechend einem **Composition-Standard** ohne Änderung mit anderen Komponenten verknüpft und ausgeführt werden kann.

**Eigenschaften**
- Eigenständig ausführbare Softwareeinheit.
- Über Schnittstelle in ihrer Umgebung austauschbar definiert.
- Unabhängige Entwicklung.
- Kunden- / anwendungsspezifisch, bzw. wiederverwendbare Software sowei Componentes-off-the-shelf (COTS)
- Können installiert bzw. deployed werden.

Eine Komponente ist vollständig und als ganzes ersetzbar. Dadurch entsteht auch eine **Kapselung**.
## Modellierung
![[Komponente.png]]
Die Modellierung von **Subsystemen** in UML kann auch verschachtelt sein:
![[Nested_component.png]]
Der Stereotyp `<<subsystem>>` ist in der Modellierung identisch zu `<<component>>`.

## Wiederverwendung
Komponenten sind dazu ausgelegt, wiederverwendet zu werden. Sie verpacken versteckte Komplexität.

Sie reduzieren die Auslieferungszeit:
- wiederverwenden ist schneller als selbst bauen.
- Weniger Tests notwendig.

Die Konsistenz wird durch Komponente erhöht, da Standard wiederverwendet werden. Ebenfalls kann immer die "beste" Komponente ausgewählt werden.

## Verhaltensschicht
Weil Komponenten ausführbare SW-Einheiten sind, lässt isch mir ihrer Hilfe das Systemverhalten auf einer höhreren Flughöhe veranschaulichen.
- **Componentes & Connector**: ausführbare Einheiten und gemeinsame Daten
- **Datenfluss**: Datenfluss zwischen Komponenten.
- **Kontrollfluss**: Wird angestossen von...
- **Prozess:** Welche Komponenten laufen parallel
- **Verteilung:** Zuordnung der Komponente zur HW