Store-and-Forward hat zwei Charakteristika:
- **Error Checking:** Switch überprüft die Frame-Check-Sequence (FCS) auf [[CRC]]-Fehler. -> Fehlerhafte Frames werden verworfen.
- **Buffering:** Das [[Frame Forwarding|Ingress-Interface]] buffert das Frame während dem FCS-Check. Dies erlaubt dem Switch auf verschiedene Übertragungsgewschindigkeiten zu reagieren.