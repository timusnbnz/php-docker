## Zugriff auf die Seite
- Bitte zuerst Docker Desktop (siehe Erstinstallation) installieren
- Die Docker-compose.yml startet Webserver, PHP, Datenbank & PHPMyAdmin
- Dazu `docker-compose up --build` ausführen
- Webserver: [localhost:80](http://localhost:80)
- PhpMyAdmin: [localhost:8090](http://localhost:8090)
- Datenbank (per PHP): [localhost:3306](http://localhost:3306)

## Aufbau Ordner & Dateien
- In `/html/` alle Dateien zum Hosting abspeichern (HTML, CSS, PHP, JS & Assets)
- In `/db/` wird die Datenbank gespeichert, jedoch nicht mit GitHub synchronisiert
- In `/logs/` werden Logs gespeichert, jedoch nicht mit GitHub synchronisiert
- In `/nginx/` wird eine Config Datei gespeichert, sollte nicht geändert werden

## Datenbank zugreifen & Tabellen erstellen
- Mit `require_once 'config.php';` werden die Zugangsdaten geladen
- Dazu zählt `$dbHost`, `$dbName`, `$dbUser`, `$dbPass`
- Das kann verwendet werden um dann eine Verbindung aufzubauen
- Wenn der `/db/` Ordner leer ist werden beim Start durch docker-compose Tabellen angelegt
- Ihr könnt die angelegten Tabellen in `init-db.sql` anpassen
- Die Tabellen werden nach dem Löschen von `/db/` Ordnerinhalt angelegt
- Somit hat jeder von euch die gleiche Datenbankstruktur

## Ersteinrichtung

### Installation der Programme auf MacOS
Ihr benötigt folgende Programme für MacOS:
- Brew: Im Terminal eingeben: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
- Git: Im Terminal eingeben: `brew install git`
- Docker: Im Terminal eingeben: `brew install docker`
- Visual Studio Code: [Download](https://code.visualstudio.com/download) 

### Installation der Programme auf Windows
Ihr benötigt folgende Programme für Windows:
- Git [Download](https://git-scm.com/downloads/win)
- Visual Studio Code [Download](https://code.visualstudio.com/download) 
- Docker Desktop [Download](https://www.docker.com/products/docker-desktop/)

### Installation prüfen
Nach dem herunterladen und installieren prüft bitte folgendes:
- Im Terminal `git --version` eingeben
- Zeigt es die Version an? Gut
- Gibt es einen Fehler? Google oder ChatGPT

### Einrichtung Git
Nun müssen wir Git einrichten
- Im Terminal `git config --global user.name "Your Name"` eingeben, setzt in die Anführungszeichen euren Namen ein (Vollständiger Name)
- Im Terminal `git config --global user.email "your.email@example.com"` eingeben, setzt in die Anführungszeichen eure E-Mail ein (Gleiche wie bei GitHub)

### Installation des Repos
- Erstellt einen Ordner für all eure Projekte, bspw. `Coding`
- Öffnet den Ordner ins VSCode
- Klickt auf Terminal oben in der Menüleiste
- Nun solltet ihr in dem erstellen Ordner sein
- Gebt nun `git clone https://github.com/timusnbnz/php-docker.git` ein
- Nun sollte ein `php-docker` Ordner erstellt sein

### Installation der Docker Container
- Wir müssen Docker Container nutzen um den Webserver, PHP, Datenbank & PHPMyAdmin auszuführen
- Dazu in das Projekt navigieren
- Dann `docker-compose up --build` ausführen
- Nun in Docker Desktop prüfen ob die 4 Container laufen
- Beim ersten Start wird eine Datenbank mit richtigen Tabellen angelegt
