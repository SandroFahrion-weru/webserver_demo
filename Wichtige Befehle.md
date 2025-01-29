# 2. Wichtige Befehle
### **Allgemeines**
**Fehlermeldungen aufmerksam lesen!** Sie enthalten oft Hinweise zur Lösung.

## 2.1 **Linux**

### **Navigation im Dateisystem**

`pwd`: Zeigt aktuelles Verzeichnis an (**P**rint **W**orking **D**irectory)

`ls`: Infos über Datei / Verzeichnis auflisten
```bash
   ls -l <Verzeichnis>              # Detaillierte Ansicht mit Berechtigungen, Größe und Datum
   ls -a <Verzeichnis>              # Auch versteckte Dateien
   ls /etc/systemd                  # Beispiel
```
`cd`: Change Directory
```bash
   cd <Verzeichnis>                 # Wechsel in das Verzeichnis
   cd ..                            # Wechsel in das übergeordnete Verzeichnis.
   cd /                             # Wechsel ins Wurzelverzeichnis
```

### **Dateien und Verzeichnisse verwalten**

`rm`: Remove
```bash
   sudo rm -f <Dateiname>           # f = force
   sudo rm -rf <Verzeichnis>        # r = recursive
```
`touch`: Erstellt eine leere Datei
```bash
   touch <Dateiname>
```

### **Dateiinhalte anzeigen und bearbeiten**

`cat`: Datei-Inhalt anzeigen
```bash
   cat <Dateiname>                  # Zeigt den gesamten Inhalt der Datei
```
`tail`: Datei-Ende anzeigen
```bash
   tail <Dateiname>                 # Zeigt die letzten 10 Zeilen der Datei
   tail -f <Dateiname>              # Zeigt Dateiänderungen in Echtzeit an (z. B. für Logs)
```
`nano`: Datei bearbeiten
```bash
   nano <Dateiname>                 # Öffnet die Datei im Nano-Editor
```

### **Rechte und Besitzer verwalten**

`chmod`: Rechte setzen
```bash
   sudo chmod <Modus> <Dateiname>   # Beispiel: chmod 755 script.sh
```
`chown`: Besitzer ändern
```bash
   sudo chown <Benutzer:Gruppe> <Dateiname>     # Beispiel: chown root:root datei.txt
```

### **Systemüberwachung und Prozesse**

`top`: Prozesse überwachen
```bash
   top                              # Zeigt laufende Prozesse und ihre Ressourcennutzung
```
`htop`: Prozesse überwachen (benutzerfreundlich)
```bash
   htop                             # Muss installiert werden
```
`ps`: Prozesse anzeigen
```bash
   ps aux                           # Zeigt alle laufenden Prozesse
```
`kill`: Prozess beenden
```bash
   kill <PID>                       # Prozess anhand der Prozess-ID beenden
   kill -9 <PID>                    # Beenden erzwingen
```
`df`: Speicherplatz anzeigen
```bash
   df -h                            # Zeigt freien Speicherplatz auf Dateisystemen
```
`du`: Verzeichnisgröße anzeigen
```bash
   du -h <Verzeichnis>              # Zeigt die Größe eines Verzeichnisses
```

### **Netzwerkbefehle**

`ping`: Erreichbarkeit prüfen
```bash
   ping <Adresse>
```
`ip`: Netzwerkinterfaces anzeigen
```bash
   ip a                             # Zeigt Netzwerkinterfaces und ihre IP-Adressen
```
`curl`: Inhalte abrufen
```bash
   curl <URL>                       # Ruft Inhalte von einer URL ab
```
`wget`: Dateien herunterladen
```bash
   wget <URL>                       # Lädt Dateien von einer URL herunter
```
`ssh`: Remote-Login
```bash
   ssh <Benutzer>@<Server>
```

### **Pakete verwalten**

`apt`: Paketverwaltungsdienst (Debian/Ubuntu)
```bash
   sudo apt update                  # Aktualisiert die Paketlisten
   sudo apt upgrade                 # Installiert alle verfügbaren Updates
   sudo apt install <Paketname>     # Installiert ein Paket
   sudo apt remove <Paketname>      # Entfernt ein Paket
```

### **Nützliche Tools und Befehle**

`grep`: Suchen in Dateien
Optionale Flags:
- **`-r`**: Rekursive Suche.
- **`-i`**: Ignoriert Groß-/Kleinschreibung.
- **`-l`**: Gibt nur Dateinamen aus.
- **`--include="*.txt"`**: Beschränkt die Suche auf bestimmte Dateitypen.
```bash
   grep <Suchbegriff> <Datei>                                       # Beispiel: grep "Fehler" log.txt
   grep -r "Leica" /storage/backup/albums                           # Sucht rekursiv in allen Dateien und Unterverzeichnissen nach dem Begriff "Leica".
   grep -r --include="*.txt" "Leica" /storage/backup/albums         # Beschränkt die Suche auf Dateien mit der Endung `.txt`.
   grep -ri "Leica" /storage/backup/albums                          # Ignoriert Groß- und Kleinschreibung bei der Suche.
   grep -rl "Leica" /storage/backup/albums                          # Gibt nur die Namen der Dateien aus, die den Suchbegriff enthalten.
   grep -r "Leica" /storage/backup/albums > ergebnisse.txt          # Speichert die Suchergebnisse in der Datei `ergebnisse.txt`.
    
```
`find`: Datei suchen
```bash
   find <Pfad> -name <Dateiname>                                                    # Sucht nach einer Datei
   find /storage/backup/albums -type f -name "*.txt" -exec grep -H "Leica" {} \;    # Kombination von 'find' und 'grep'
```
- **`find`**: Findet Dateien basierend auf bestimmten Kriterien.
- **`-type f`**: Sucht nur nach Dateien.
- **`-name "*.txt"`**: Beschränkt die Suche auf `.txt`-Dateien.
- **`-exec ... \;`**: Führt `grep` für jede gefundene Datei aus.

`tar`: Archiv erstellen/entpacken
```bash
   tar -czf <Archivname>.tar.gz <Verzeichnis>                       # Erstellt ein komprimiertes Archiv
   tar -xzf <Archivname>.tar.gz                                     # Entpackt ein komprimiertes Archiv
```
`history`: Befehlsverlauf anzeigen
```bash
   history                          # Zeigt die letzten verwendeten Befehle
   !123                             # Führt den Befehl Nummer 123 erneut aus
```

### **Benutzerverwaltung**

`whoami`: Aktuellen Benutzer anzeigen
```bash
   whoami                           # Zeigt den aktuellen Benutzer an
```
`adduser`: Benutzer erstellen
```bash
   adduser <Benutzername>           # Erstellt einen neuen Benutzer
```
`passwd`: Passwort ändern
```bash
   passwd <Benutzername>            # Ändert das Passwort eines Benutzers
```
`su`: Benutzer wechseln
```bash
   su <Benutzername>                # Wechselt zum angegebenen Benutzer
```
`sudo`: Befehle als Admin ausführen
```bash
   sudo <Befehl>                    # Beispiel: sudo apt update
```

### **Zeit und Datum**

`date`: Datum und Uhrzeit anzeigen
```bash
   date                             # Zeigt das aktuelle Datum und die Uhrzeit an
```
`timedatectl`: Zeitzone konfigurieren
```bash
   timedatectl                              # Zeigt die aktuelle Zeitkonfiguration
   timedatectl set-timezone Europe/Berlin   # Zeitzone setzen
```

## 2.2 **Git**

### **Grundlagen**

`git init`: Erstellt ein neues Repository im aktuellen Verzeichnis.
```bash
git init
```

`git clone`: Klont ein bestehendes Repository.
```bash
git clone <Repository-URL>
```

`git status`: Zeigt den aktuellen Status des Repositories an.
```bash
git status
```

`git add`: Fügt Dateien zur Staging-Area hinzu.
```bash
git add <Datei>
git add .   # Alle Änderungen hinzufügen
```

`git commit`: Speichert die Änderungen aus der Staging-Area als lokalen Commit.
```bash
git commit -m "Beschreibung der Änderungen"
```

`git log`: Zeigt die Commit-Historie an.
```bash
git log
git log --oneline   # Kurzformat
```

### **Branching und Zusammenführen**

`git branch`: Zeigt oder erstellt Branches.
```bash
git branch                    # Listet alle lokalen Branches auf
git branch -a                 # Listet alle Branches auf
git branch <neuer-branch>     # Erstellt einen neuen Branch
```

`git checkout`: Wechselt den Branch.
```bash
git checkout <branch-name>
git checkout -b <branch-name>    # Wechsel auf neu erstellten Branch
```

`git switch`: Alternativ zu `checkout` für Branch-Wechsel.
```bash
git switch <branch-name>
```

`git merge`: Führt Branches zusammen.
```bash
git merge <branch-name>
```

`git rebase`: Ändert die Commit-Historie eines Branches.
```bash
git rebase <branch-name>
```

### **Remote-Repositories**

`git remote`: Remote-Repositories verwalten.
```bash
git remote -v   # Zeigt die konfigurierten Remote-Repositories an
```

`git push`: Änderungen zu einem Remote-Repository senden.
```bash
git push origin <branch-name>
git push                         # Push auf aktuellem Branch
```

`git pull`: Änderungen vom Remote-Repository abrufen und mergen.
```bash
git pull origin <branch-name>
git pull                         # Pull auf aktuellem Branch
```

`git fetch`: Holt Änderungen vom Remote-Repository, wendet sie aber nicht an.
```bash
git fetch origin
```

### **Zurücksetzen und Wiederherstellen**

`git reset`: Setzt Änderungen zurück.
```bash
git reset HEAD~1           # Letzten Commit zurücksetzen (Änderungen bleiben)
git reset --hard HEAD~1    # Letzten Commit komplett verwerfen
```

`git revert`: Macht einen bestimmten Commit rückgängig.
```bash
git revert <commit-hash>
```

`git stash`: Speichert uncommittete Änderungen vorübergehend.
```bash
git stash                  # Speichert aktuelle Änderungen
git stash pop              # Wendet gespeicherte Änderungen wieder an
```

## 2.3 **Docker**

### **Grundlagen**

`docker --version`: Überprüft die installierte Docker-Version.
```bash
docker --version
```

`docker info`: Zeigt Informationen über die Docker-Installation und den aktuellen Status an.
```bash
docker info
```

### **Container verwalten**

`docker run`: Startet einen neuen Container.
```bash
docker run <image-name>
docker run -d -p 8080:80 <image-name>  # Im Hintergrund mit Port-Mapping
```

`docker ps`: Listet aktive Container auf.
```bash
docker ps
docker ps -a   # Zeigt auch gestoppte Container
```

`docker stop`: Stoppt einen laufenden Container.
```bash
docker stop <container-id>
```

`docker start`: Startet einen gestoppten Container neu.
```bash
docker start <container-id>
```

`docker restart`: Startet einen Container neu.
```bash
docker restart <container-id>
```

`docker rm`: Entfernt einen gestoppten Container.
```bash
docker rm <container-id>
```

### **Images verwalten**

`docker images`: Listet verfügbare Docker-Images auf.
```bash
docker images
```

`docker pull`: Lädt ein Image aus einer Registry (z. B. Docker Hub).
```bash
docker pull <image-name>
```

`docker rmi`: Entfernt ein Docker-Image.
```bash
docker rmi <image-name>
```

### **Volumes und Speicher**

`docker volume`: Verwaltung von Volumes.
```bash
docker volume ls        # Listet Volumes auf
docker volume rm <name> # Löscht ein Volume
```

### **Netzwerk**

`docker network ls`: Listet verfügbare Netzwerke auf.
```bash
docker network ls
```

`docker network create`: Erstellt ein neues Netzwerk.
```bash
docker network create <network-name>
```

`docker network inspect`: Zeigt Details eines Netzwerks an.
```bash
docker network inspect <network-name>
```

### **Logs und Monitoring**

`docker logs`: Zeigt die Logs eines Containers.
```bash
docker logs <container-id>
```

`docker stats`: Zeigt die Ressourcen-Nutzung von Containern.
```bash
docker stats
```

### **Docker Compose**

`docker compose up`: Startet die Container gemäß `docker-compose.yml`.
```bash
docker compose up
docker compose up -d  # Im Hintergrund starten
```

`docker compose down`: Stoppt und entfernt die Container.
```bash
docker compose down
```

`docker compose ps`: Zeigt den Status der laufenden Services.
```bash
docker compose ps
```

`docker compose logs`: Zeigt die Logs aller Container.
```bash
docker compose logs
```

`docker compose build`: Erstellt die Images aus einer `docker-compose.yml`.
```bash
docker compose build
```

### **Beispiel `docker-compose.yml` für einen Webserver**

```yaml
services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html
```
