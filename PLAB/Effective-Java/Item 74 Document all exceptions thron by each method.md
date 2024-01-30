Es sollten alle [[Exceptionhandling|Exceptions]] dokumentiert werden, welche von einer [[Methode]] geworfen werden können. Dies beinhaltet sowohl checked als auch unchecked Exceptions.

Es sollten alle checked Exceptions **einzeln** sowie auch die Bedingungen welche zu der Exception führen dokumentiert werden. (Mit dem Java-Doc-Tag `@throws`)

Auch unchecked Exceptions sollten mittels `@throws` dokumentiert werden, jedoch nie als `...() throws` definiert werden.
Da unchecked-Exceptions mehrheitlich Programmierfehler sind, hilft eine Dokumentation dieser möglichen Fehler, dass diese nie gemacht werden.


>[!info]
>Wird dieselbe Exception bei vielen [[Methode|Methoden]] derselben [[Klasse]] aus demselben Grund geworfen, kann diese im Klassenheader dokumentiert werden, anstatt überall dupliziert zu werden.
 