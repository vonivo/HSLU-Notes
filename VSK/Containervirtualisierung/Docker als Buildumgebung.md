>[!Definition]
>[[Docker]] ist als Buildumgebung sehr praktisch, da sehr einfach die richtige JDK (in der richtigen Version) sowie das richtige [[Build-Werkzeug]] verfügbar ist.

Viele Projekte bieten für ihre Produkte fertige Images an. z.B.:
- `3.9.9-eclipse-temurin-21`
- `3.9.9-amazoncorretto-21`
- `3.9.9-openjdk-21`

>[!Info]
>Sehr gute Eignung für den [[Buildprozess]]
- Kein Switching von JDK-Versionen nötig (einfach anderes Image)
- Standardisierte Entwicklungsbasis für alle Entwickler


## .m2-Repo mounten
```sh
~% docker volume create maven-repo
~%docker run -it --rm --workdir "/work" -v "%cd%:/work" -v "maven-repo":/root/.m2
```

## Netzwerk-Port freigeben
```
docker run -d -p "5555:5555" rgisler/echoserve
```