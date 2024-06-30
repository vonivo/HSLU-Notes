Die Datenübertragungsrate ist die Datenmenge welche pro Zeit übertragen werden kann.
Sie wird gemessen in Bit/s, kbit/s Mbit/s, Gbit/s jeweils Faktor $1000$.

Bei der Datenübertragungsrate wird unterschieden in:
- **Datenübertragungsrate, Kanalkapazität, Bandbreite, Durchsatz**
	-> Übertragungsrate, die das Netzwerk liefert
	-> Eigenschaft des Kanals
- **Bitrate, natürliche Bitrate, Datenrate**
	->Datenrate die der Dienst effektiv benötigt.


# Typische Datenübertragungsraten

| Technologie                        | Rate                     |
| ---------------------------------- | ------------------------ |
| Moden / Dialup                     | bis 56 kbit/s            |
| Mobildfunk GSM-GPRS                | bis 53,6 kbit/s          |
| ADSL                               | 8-24 Mbit/s              |
| Ethernet ([[Koaxialkabel]], Cat 3) | 10 Mbit/s                |
| Mobilfunkt 3G: UMTS /HSPA          | 384 kbit/s bis 42 Mbit/S |
| WLAN 802.11g                       | 54 Mbit/s                |
| Fast Ethernet                      | 100 Mbit/s               |
| USB 2.0 / 3.0                      | 480 Mbit/s / 2.4 Gbit/s  |
| HDMI1.3                            | 8.1 bis 10.2 Gbit/s      |
| HDMI 2.1                           | 38.4 Gbit/s              |
| WLAN 802.11n                       | bis 600 Mbit/s           |
| Mobilfunk 4G: LTE / LTE-A          | 300 Mbit/s / 1000 Mbit/s |
| Mobilfunk 5G                       | Bis 10 Gbit/s            |

# Typische Bitraten bei Anwendungen

| Dienst                              | E\[s(t)]        | B      |
| ----------------------------------- | --------------- | ------ |
| Sprache                             | 32-64 kbit/s    | 2      |
| Interative DAten (einfaches Surfen) | 1 - 100 kbit/S  | 10-100 |
| Masssendaten (Streaming)            | 1-10 Mbit/s     | 1-10   |
| Standard Video (Teams, Zoome)       | 1.5 - 15 Mbit/s | 2-10   |
| High Definition TV                  | 15-150 Mbit/s   | 1-2    |

Die Fluktuation setzt sich wie folgt zusammen:
$$
B = \frac{S}{E}
$$
$B$ -> Fluktuation (Mass für das Schwanken der Bitrate)
$S$ -> Spitzenwert
$E$ -> Durchschnittswert

Damit die Fluktuation reguliert werden kann, können Daten mit einer konstanten Bitrate (CBR) oder einer variablen Bitrate (VBR) kodiert werden.

Bei einer CBR wird die Qualität temporär reduziert, um die maximale Rate nicht zu überschreiten.


# Latenzzeit
Die Latenzzeit beschreibt die Zeit, die der ganze Datenpakt benötigt, um vollständig beim Empfänger anzukommen (one way latency).

$$
Latenz = \frac{Distanz}{\text{Ausbreitungsgewschindigkeit}} + \frac{Paketgrösse}{Durchsatz} + Wartezeit
$$

Beispiel:
Distand: 20km
Ausbreitungsgeschwindigkeit: 200'000 km/s
Paketgrösse: 100 Bit
Datenrate: 1000 Mbit/s

Dauer für ein Signal von a nach b:
$$
\begin{align}
Zeit &= \frac{20km}{\frac{200'000km}{s}} \\
&=\frac{1}{10'000}s \\
&=0.0001s \implies 0.1 ms
\end{align}
$$

Entfernung von erstem und letzten Bit
$$
\begin{align}
\text{Enfernung in s} &= \frac{100bit}{\frac{1'000Mbit}{s}}  \\
\text{Enfernung in s} &= \frac{100bit}{\frac{1'000'000'000bit}{s}} \\
\text{Enfernung in s} &= \frac{1bit}{\frac{10'000'000bit}{s}} \\
&=0.0000001s \\
&=0.0001 ms
\end{align}
$$
Distanz von erstes Paket nach $0.0001$ ms
$$
\begin{align}
&=\frac{200'000km}{s} \times 0.0000001s \\
&=2km \times 0.01 \\
&=2000m \times 0.01 \\
&= 20m
\end{align}
$$
