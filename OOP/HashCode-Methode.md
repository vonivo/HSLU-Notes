- Eine Hashfunktion ist eine Abbildung, die eine grosse Eingabe- (daten-)menge auf eine sehr viel kleinere Zielmenge (den Hashwert) abbildet. 
- Eine gute Hashfunktion liefert selbst für kleinste Änderungen in den Eingabedaten einen anderen Hashwert. (Avalanche-Effekt)
- Die (nicht mögliche) perfekte Hashfunktion würde für alle unterschiedlichen Eingabedaten auch unterschiedliche Hashwerte liefern, in der Realität können aber **immer** Kollisionen auftreten!

>[!info]
>Diese Methode wird zusammen mit der [[Equals-Methode]] von vielen Java-Collections verwendet, und ist **fundamental wichtig** für deren **korrekte** und **performante** Funktion.

## HashCode-Vertrag
- Sind zwei Objekte im Sinne von `equals()` gleich, **müssen** auch die Hashwerte identisch sein.
- Sind zwei Objekte im Sinne von `equals()` **ungleich**, sollten sie idealerweise **verschiedene** Hashwerte liefern
- Konsistenz: Wird das Objekt nicht verändert, darf sich bei wiederholtem Aufruf von `hashCode()` der Hashwert nicht verändern.
## Beispielimplementation
```
@Override
public int hashCode(){
	return Objects.hash(this.name, this.lastname);
}
```
>[!warning]
>In der `hashCode()`-Funktion sollten nur Attribute gehasht werden, welche auch in der `equals()`-Methode überprüft werden.

