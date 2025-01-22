# Webserver-Demo Dokumentation

## Inhaltsverzeichnis
1. [Einleitung](#einleitung)
2. [Ziele der Demo](#ziele-der-demo)
3. [Systemübersicht](#systemübersicht)
4. [Vorbereitung](#vorbereitung)
5. [Schritt-für-Schritt-Anleitung](#schritt-für-schritt-anleitung)
    - [Server-Einrichtung](#server-einrichtung)
    - [Webserver-Installation](#webserver-installation)
    - [Beispielseite bereitstellen](#beispielseite-bereitstellen)
6. [Testen der Installation](#testen-der-installation)
7. [Fehlerbehebung](#fehlerbehebung)
8. [Zusätzliche Hinweise](#zusätzliche-hinweise)
9. [Passwörter und Zugangsdaten](#passwörter-und-zugangsdaten)
10. [Ressourcen](#ressourcen)

---

## Wichtige Befehle
1. Systemauslastung der Docker Container überwachen:
   ```bash
   docker stats
2. docker ps:
   ```bash
   docker ps
1. Systemauslastung der Docker Container überwachen:
   ```bash
   docker stats
1. Systemauslastung der Docker Container überwachen:
   ```bash
   docker stats
1. Systemauslastung der Docker Container überwachen:
   ```bash
   docker stats
1. Systemauslastung der Docker Container überwachen:
   ```bash
   docker stats
---

## Ziele der Demo
- Verstehen der grundlegenden Komponenten eines Webservers.
- Installieren und Konfigurieren eines Webservers (z. B. Nginx oder Apache).
- Bereitstellen und Testen einer statischen HTML-Seite.
- Grundlegende Fehlerbehebung.

---

## Vorbereitung
### Erforderliche Software
- Texteditor (Visual Studio Code)
- SSH-Client (z. B. PuTTY, Terminal oder VS Code)

### Voraussetzungen
- Internetzugang

---

## Schritt-für-Schritt-Anleitung


### Windows 11 Home via Rufus
[https://rufus.ie/de/](https://rufus.ie/de/)

#### In BIOS/UEFI
- **Virtualisierungstechnologie aktivieren** (z.B. Intel Virtualization Technology)

#### Internetzugriff
- Via LTE-Router

#### Grafikkarte
- Aktuelle Nvidia Studio Treiber installiert

#### Windows-Features nachinstalliert:
- Virtual Machine Platform
- Windows-Hypervisor-Plattform
- Windows-Subsystem für Linux

### WSL (Windows Subsystem for Linux)
1. **In CMD ausführen:**  
   `WSL.exe --update`
2. **Installation prüfen:**  
   `C:\Users\install>wsl --version`

   Ausgabe sollte etwa so aussehen:  
   ```
   WSL-Version: 2.3.26.0  
   Kernelversion: 5.15.167.4-1  
   WSLg-Version: 1.0.65  
   MSRDC-Version: 1.2.5620  
   Direct3D-Version: 1.611.1-81528511  
   DXCore-Version: 10.0.26100.1-240331-1435.ge-release  
   Windows-Version: 10.0.26100.1742  
   ```

### Downloads – Oracle VirtualBox
- **Extension Pack**
- **User Guide**
- **Host App**
- VirtualBox Guest Additions ISO  
  [Oracle VM VirtualBox - Downloads | Oracle Technology Network](https://www.oracle.com)

#### Guest Additions installieren:
1. VM in VirtualBox starten
2. Im Fenstermenü unter **"Geräte"**
3. **"Optische Laufwerke"** und dann die `VBoxGuestAdditions.iso` auswählen
4. Alternativ: Direkt auf **"Gasterweiterungen einlegen..."**

### Windows Server 2022
- **Evaluation Edition**
- Desktop Experience
- 180 Tage Laufzeit, 3x verlängerbar (= 540 Tage)

#### Laufzeit verlängern:
1. In PowerShell:
   `slmgr.vbs /rearm`

### VS Code Extensions:
- Docker
- WSL
- YAML

### Weitere Software:
- Git installiert
- TeamViewer Host installiert

### Docker
[Docker Desktop - Installation für Windows](https://docs.docker.com/desktop/setup/install/windows-install/)

