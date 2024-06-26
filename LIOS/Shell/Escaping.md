Für die [[Bash]] besitzen einige Zeichen eine besondere Bedeutung. Es kann vorkommen, dass die Zeichen aber wörtliche verwendet werden sollen. Dafür gibt es das Escaping.

Dafür gibt es drei Methoden:
- Der Backslash `\`
- einfach Anführungszeichen `''`
- doppelte Anführungszeichen `""`

# Backslash
Der Backslash entfernt die spezielle Bedeutung des **darauffolgenden Zeichens**.

```bash
[user@host ~]$ echo # a comment


[user@host ~]$ echo \# not a comment
# not a comment
```

# Doppelte Anführungszeichen
Die doppelten Anführungszeichen verhindern, dass die [[Bash Shellextension]] Globbingdurchführt, erlaubt jedoch noch die Befehls- und Variabelsetzung.
```bash
[user@host ~]$ echo *.txt
file1.txt file2.txt

[user@host ~]$ echo "*.txt"
*.txt

[user@host ~]$ echo "Your Username is '$USER'"
Your Username is 'user'.
```

# Einfach Anführungszeichen
Einfache Anführungszeichen bewirken, dass alles zwichen ihnen wörtlich interpretiert wird.

```bash
[user@host ~]$ echo 'Keine Variabeln werden ausgegeben: $USER'
Keine Variabeln werden ausgegeben: $USER
```

