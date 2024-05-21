Da moderne Speicher in Worten organisiert sind, (Es wird nicht nur eine [[Speicherzelle]] abgefragt, sondern mehrere [[Speicherorganisation#Organisation|Speicherorganisation]]), gibt es nun 2 Arten wie Zahlen gespeichert werden können.

## Big-Endian
Beim Big-Endian wird das **höchstwertige Byte zuerst** abgespeichert.

Beispiel: 32-bit Zahl 0x1A2B34D
![[BigEndian.png]]
Das höchstwertige Byte 1A wird in die Speicherzelle mit dem tiefsten Index gespeichert.

## Little-Endian
Beim Little-Endian wird genau umgekehrt vorgegangen, sprich das höchstwertige Byte kommt zum Schluss.

Beispiel: 32-bit Zahl 0x1A2B34D
![[Little-Endian.png]]

# Kontrollfragen
#flashcards/Rechenarchitekturen 

**Was ist ein Cache?**
?
Schneller Pufferspeicher. Enthält Kopien von Inhalten eines anderen (Hintergrund) Speichers und beschleunigt den Lesezugriff.

**Was versteht man unter einem Big-Endian?**
?
Dass die höchstwertige Stelle zuerst abgespeichert wird.

**Schreiben Sie das aktuelle Datum und die Uhrzeit in Big-Endian-Format?**
?
2024-05-20 17:15:00