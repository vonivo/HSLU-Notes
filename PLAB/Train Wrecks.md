Train Wrecks sind Code-Snippets welche verschiedene Funktionen zusammenkoppeln wie Wagons von Zügen:
```java
final String outputDir = ctxt.getOptions().getScratchDir().getAbsolutePath();
```
Es ist am besten dies so aufzuteilen:
```java
Options opts = ctxt.getOptions();  
File scratchDir = opts.getScratchDir();  
final String outputDir = scratchDir.getAbsolutePath();
```

Train-Wrecks verletzen Potenziell die [[Law of Demeter]]. Dabei muss unterschieden werden ob es sich um eine [[Object Anti-Symmetrie|Datenstruktur]] oder ein [[Object Anti-Symmetrie|Objekt]] handelt.