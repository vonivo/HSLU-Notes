>[!Definition]
>Ein verteiltes System kann maximal zwei der folgenden Garantien einhalten:
>- **Consistency**
>- **Availability**
>- **Partition Tolerance**

![[CAP_Theorem.png]]
- **Konsistenz**: Alle beteiligten Systeme habe identische und aktuelle Daten.
- **Verfügbarkeit:** Daten sind für alle Lese- und Schreiboperationen sofort bereit.
- **Aufteilungstoleranz:** System kann trotz Aufteilung in zwei oder mehr bzgl. Kommunikation getrennte Partitionen weiter operieren.

## AP-Systeme
![[AP-System.png]]
AP-Systeme kommunizieren trotz ausgefallener Kommunikation weiter.
Dies führt zu **Reduktion der Konsistenz**.

**Beispiel**
- DNS
- Consumer Filesynchronisation

## CP-System
![[CP-System.png]]
CP-Systeme operieren trotz ausgefallener Kommunikation weiter, aber nur soweit die Konsistenz gewährleistet ist.
Die führt zu **Reduktion der Verfügbarkeit**

**Beispiel**
- Email
- Bankomat

## CA-System
![[CA-System.png]]
CA-Systeme bieten sowohl Konsistenz als auch Verfügbarkeit und dürfen darum nicht partitioniert werden.

Dies führt zu **Reduktion der Partitionstoleranz**

**Beispiel**
- Webabpplikation
