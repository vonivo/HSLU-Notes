Das Interface Segregation Principle besagt, dass [[Klasse|Klassen]] nicht [[Methode|Methoden]] eines [[Interface]] implementieren müssen, welche sie nicht benötigen.

## Beispiel
![[ISP.png]]
Die Klassen `BankPayment` und `LoanPayment` basieren beide auf dem Inteface `Payment`. Dabei wird von der Klasse `BankPayment` nur die Methoden `inititatePayments`, `status` und `getPayments` implementiert. Die beiden anderen Funktionen ergeben eine `UnsupportedOperationException`. 

Ähnliches ist bei der Klasse `LoanPayment` dort ergibt die Funktion `initiatePayments` eine `UnsupportedOperationException`. **Sprich das Interface ist verschmutzt.**

Wenn nun eine dritte Klasse hinzukommt, welche wieder eine neue Methode benötigt, und diese dem `Payment`-Interface hinzugefügt wird, muss sowohl die Klasse `BankPayment` und `LoanPayment` geändert werden. (**Auch wenn diese nicht betroffen sind.**)



Um nun das ISP anzuwenden, wird die Interfacevererbung zunutze gemacht.
![[ISP_2.png]]
Nun muss keine Klasse mehr eine Methode implementieren, die sie nicht benötigt.