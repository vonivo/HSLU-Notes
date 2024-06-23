Pipes manipulieren die [[Programmoutputumleitung|Umleitung]] der Standardeingabe und der Standardausgabe.

Pipes sende die Standardausgabe eines Prozesses an die Standardeingabe eines anderen Prozesses:
```bash
[labstudent@lios-1 ~]$ cat /etc/passwd | wc -l
```

![[Pipe.png]]