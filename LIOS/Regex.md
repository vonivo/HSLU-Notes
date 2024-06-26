Reguläre Ausdrücke bieten eine Musterabgleich, der das Auffinden bestimmter Inhalte erleichtert. Viele [[Prompt|Befehle]] in [[Linux]] können damit umgehen.
Bsp:
- `vim`
- `grep`
- `less`

Der Name `grep` leitet sich sogar vom Ausdruck *Global regular expression print* ab.


| Option       | Beschreibung                                                                                |
| ------------ | ------------------------------------------------------------------------------------------- |
| `.`          | Matches any single character                                                                |
| `?`          | The preceding item is optional and will be match at most once                               |
| `*`          | Thre preceding item will be matched zero or more times                                      |
| `+`          | The preceding item will be match one or more times                                          |
| `{n}`        | The preceding item is matched exactly $n$ times                                             |
| `{n,}`       | The preceding item is matched $n$ or more times                                             |
| `{,m}`       | The preceding item is matched at most $m$ times                                             |
| `{n,m}`      | The preceding item is matched at least $n$ times, but not more than $m$ times               |
| `[:alnum:]`  | Alphanumeric charachters: `[:alpha`] and `[:digit]`; In 'C' and ASCII same as `[0-9A-Za-z]` |
| `[:alpha:]`  | Alphabetic charaters: `[:lower]` and `[:upper]`                                             |
| `[:blank:]`  | Blank characters: space and tab                                                             |
| `[:cntrl:]`  | Control characters. In ASCII octal codes 000 through 037 and 177                            |
| `[:digit:]`  | Digit                                                                                       |
| `[:graph:]`  | Graphical characters: `[:alnum]` and `[:punct]`                                             |
| `[:print:]`  | Printable characters: `[:alnum]` and`[:punct]`                                              |
| `[:punct:]`  | Punctuation characters                                                                      |
| `[:space:]`  | Space characters: tab, newline, vertical tab, form feed, carriage return and space          |
| `[:xdigit:]` | Hexadecimal digits                                                                          |
| `\b`         | Match emtpy string at edge of word                                                          |
| `\B`         | Match the empty string provided it is not at the edge of a word                             |
| `\<`         | Match the empty string at the beginning of word                                             |
| `\>`         | atch the empty string at the end of word                                                    |
| `\w`         | Match word constituent. Synonym for `[_[:alnum:]]`                                          |
| `\W`         | Match word constituent. Synonym for `[^_[:alnum:]]`                                         |
| `\s`         | Match white space                                                                           |
|              |                                                                                             |

## Beispiel `grep`
```bash
[vonivo@lt-vonivo ~]$ grep  localhost /etc/hosts 
127.0.0.1  localhost
::1        localhost ip6-localhost ip6-loopback
```
- `-i` -> Ignore-Case
- `-v`-> Negation