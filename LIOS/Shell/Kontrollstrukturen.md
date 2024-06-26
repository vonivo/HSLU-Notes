Damit [[Shell-Scripting|Skripte]] nicht nur eine Verkettung von [[Prompt|Befehlen]] ist, existieren auch Schleifen und Verzweigungen.

# if/then-Konstrukt
```bash
if <Condition>; then
	echo "Inside If-Case"
else
	echo "Inside Else-Case"
fi
```
Wichtig hierbei ist, dass die `<Condition>` ein eigenes Programm ist, welches ausgeführt wird. Ist der **Exit-Code des Programms =0** wird der **If-Case** ausgeführt.

Exitcode = 0 -> If-Case
Exitcode = 1 -> Else-Case

Das Ganze kann auch mit einem Else-If verbunden werden:
```bash
if <Condition>; then
	echo "Inside If-Case"
elif <Second Condition>; then
	echo "Inside Else-If"
else
	echo "Inside Else-Case"
fi
```

# Schleifen
## While
```bash
while <Condition>
do
	echo "Inside while"
done
```

## Unitl
Ähnlich wie der While Loop, jedoch wird der Loop so lange ausgeführt bis die Bedingung zutrifft.
```bash
until <Condition>
do
	echo "Inside until"
done
```

# For
```bash
for i in {1..5}
do
	echo "Inside for"
done
```


# Test-Programm
Das Programm `test` setzt den Rückgabewert je nach Bedingung. Wird bei Kontrollstrukturen verwendet, um eine Bedingung zu überprüfen.

```bash
[user@host ~]$ test "ture" = "true"
0

[user@host ~]$ test "true" = "fasle"
1
```

Damit das Programm einfach in Skripts verwendet werden kann, existiert dafür ein Shortcut `if [ $var = $seconVar ]`

```bash
if [ $var -eq 1 ]; then
	echo "Inside If-Case"
else
	echo "Inside Else-Case"
fi
```

>[!error] Achtung
>Die Abstände von und nach `[`/`]` sind zwingend.


