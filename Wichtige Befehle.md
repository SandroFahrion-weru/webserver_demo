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

## 2.3 **Docker**

`stats`: Systemauslastung der Docker Container überwachen:
```
   docker stats
```
