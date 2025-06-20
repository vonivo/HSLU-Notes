SonarQube ist eine Webapplikation mit zentralen Regelsets.
Dadurch lassen die Projekte dezentral analysieren
- Vereinfachte SQALE-Methodik -> berücksichtigt auch dynamische Analysen
- Kann als harte Q-Gate genutzt werden
- SQALE Methodik als Plugin

Es gibt eine SonarQube Community Edition -> am besten in einem Docker Container mit DB verwenden

Folgendes Docker Compose File kann für den Einsatz von SonarQube verwendet werden
```yaml
services:
  sonarqube:
    depends_on:
      - db
    image: sonarqube:community
    restart: unless-stopped
    ports:
      - "9000:9000"
      - "9092:9092"
    networks:
      - sonarnet
    environment:
      - SONAR_JDBC_URL=jdbc:postgresql://db:5432/sonarqube
      - SONAR_JDBC_USERNAME=sonarqube
      - SONAR_JDBC_PASSWORD=sonarpass
    volumes:
      - vsk_sonarqube_conf:/opt/sonarqube/conf
      - vsk_sonarqube_data:/opt/sonarqube/data
      - vsk_sonarqube_extensions:/opt/sonarqube/extensions
      - vsk_sonarqube_plugins:/opt/sonarqube/lib/bundled-plugins
  db:
    image: postgres:16
    networks:
      - sonarnet
    environment:
      - POSTGRES_DB=sonarqube
      - POSTGRES_USER=sonarqube
      - POSTGRES_PASSWORD=sonarpass
    volumes:
      - vsk_sonarqube_db:/var/lib/postgresql
      - vsk_postgresql_data:/var/lib/postgresql/data
networks:
  sonarnet:
    driver: bridge
volumes:
  vsk_sonarqube_conf:
  vsk_sonarqube_data:
  vsk_sonarqube_extensions:
  vsk_sonarqube_plugins:
  vsk_sonarqube_db:
  vsk_postgresql_data:
```
=> Es werden auch gleich Netzwerke und persistente Volumes definiert

Um den Docker zu starten/stoppen/loggen:
```
docker compose up –d
docker compose down
docker compose logs -f
```

Um eine Analyse durchzuführen 
- Dafür muss aber eine token unter http://localhost:9000/account/security gelöst werden was als Parameter an mvn übergeben wird
- `mvn sonar:sonar -D"sonar.host.url=http://localhost:9000" -D"sonar.token=sqa_token`

IDE Plugin SonarLint ist frei verfügbar.