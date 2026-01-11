Wenn ein System aus vielen kleinen [[Microservice|Microservices]] besteht können diese Services nicht mehr auf einen:
- dedizierten HW-Stack
- Voller VM-Stack mit eigenen [[Betriebssysteme|Betriebssystem]]
- Individuell gepflegte spezifische Docker-Container
deployt werden.

Dies hat vor allem folgende Gründe:
- Ressourcenverbrauch wäre viel zu hoch
- Arbeitsaufwand für Erstellung, Wartung und Betrieb viel zu hoch muss zwingend automatisiert werden.

=> **Lösung**: Docker-Images und -Container, oder gar "serverless" sind absolut zwingend.