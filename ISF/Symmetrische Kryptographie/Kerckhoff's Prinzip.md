Ein Angreifer kennt den Algorithmus und alle Details des Systems. Nur der Schlüssel ist geheim.

>[!Definition]
>Ein sicheres Verschlüsselungsschema $M,C,K,f,f^{*}$ muss folgende Angriffe überstehen:
>1.  **Ciphertext-Only-Attacke**: Der Angreifer kennt eine begrenzte Anzahl von Geheimtexten. (Davon kann man immer ausgehen)
>2. **Known-Plaintext-Attacke**: Der Angreifer kennt eine begrenzte Anzahl von Geheimtexten mit den zugehörigen Klartexten.
>3. **Chosen-Plain-Text-Attacke**: Der Angreifer hat die Möglichkeit zu einem (von ihm ausgewählten) Klartext den zugehörigen Geheimtext zu gelangen (Angreifer ist im Besitz des Verschlüsselungsapparates).
>4. **Chose-Ciphertext-Attacke**: Der Angreifer hat die Möglichkeit zu einem (von ihm ausgewählten) Geheimtext an den zugehörigen Klartext zu gelangen.
