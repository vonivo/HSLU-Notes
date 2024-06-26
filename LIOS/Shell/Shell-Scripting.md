---
aliases:
  - Script
  - Skript
---
Da viele administrative Aufgaben in [[Linux]] mit der [[Terminal#Kommandozeile|Kommandozeile]] gemacht werden und diese Aufgaben oft eine Verkettung von [[Prompt|Befehlen]] ist, kann dies über ein **Shell-Script** gemacht werden.

In der einfachsten Form ist das ein File mit einer Liste von Befehlen, welche nacheinander ausgeführt werden.

# Hash-Bang / Shebang
Die erste Zeile in jedem Shell-Script definiert den [[Terminal#Interpreter|Interpreter]] welcher für das Skript verwendet wird.

**Variante 1**
Es wird empfohlen diese Variante zu verwenden, da durch die Angabe des `env`-Verzeichnisses alle Umgebungsvariablen korrekt erstellt werden.

`#!/usr/bin/env bash`

**Variante 2**
Diese Variante kann ebenfalls verwendet werde, jedoch existieren keine Umgebungsvariablen.
`#!/bin/bash`

# Ausführen
Ein Skript kann wie ein binäres Programm ausgeführt werden:
`[user@host ~]$ bash script.sh`

Wenn dem Skript die `execute` [[Permission|Berechtigung]] gegeben wird, kann es sogar so ausgeführt werden:
`[user@host ~]$ ./script.sh

Alternativ kann das Skript auch zum `$PATH` hinzugefügt werden, um von überall auf dem System  ausgeführt zu werden.



# Ausgaben
Um Ausgaben in einem Script zu täten, wird der Befehl `echo` verwendet. Damit Fehlermeldungen den richtigen [[Programmoutputumleitung|Dateidescriptor]] finde, sollte [[Programmoutputumleitung]] verwendet werden.

**Beispiel Info-Meldung**
`echo "INFO: Das ist eine Info Meldung"`

**Beispiel Error-Meldung**
`echo "Das ist ein Fehler" >&2`

# Variablen
Eine Shell-Skript-Variable wird erstellt, sobald ihr einen Inhalt zugewiesen wird. Die Variable ist bis zum Ende des Skripts gültig.

Variablen können einen Datentyp vorgestellt haben, wird jedoch selten verwendet.

**Beispiel**
```bash
# Initialisierung
File1=/etc/passwd
File2=/etc/shadow
Destination=/root

# Verwendung
cp $File1 $File2 $Destination
```

## Umgebungsvariablen
Umgebungsvariablen und Systemvariablen sind Variablen, welche das System für den Betrieb verwendet. Konventionell werden diese **in Grossbuchstaben** geschrieben.

Diese Variablen können auch geändert werden, davon wird jedoch abgeraten.

- `env` -> Zeit alle Umgebungsvariablen
- `set` -> Zeit alle Systemvariablen 

| Variabel                     | Wirkweise                                                                                                   |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `$HOSTNAME`                  | Hostname der Maschine                                                                                       |
| `$USER, $USERNAME, $LOGNAME` | Name des Benutzers der Sitzung                                                                              |
| `$PATH`                      | Liste aller Verzeichnisse, die der Interpreter durchsucht, wenn vor einem Befehl kein Pfad angegeben wurde. |
| `$PWD`                       | Aktuelles Verzeichnis                                                                                       |
| `$HOME`                      | Login-Verzeichnis / Home-Dir                                                                                |
| `$$`                         | Prozess-ID der Skript-Ausführung                                                                            |
| `$?`                         | Exit-Code des zuletzt ausgeführten Befehls                                                                  |


