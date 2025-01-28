# Azubi Laborumgebung

## Inhaltsverzeichnis
- [Azubi Laborumgebung](#azubi-laborumgebung)
    - [Inhaltsverzeichnis](#inhaltsverzeichnis)
- [1. Übersicht](#1-übersicht)
    - [1.1 Host](#11-host)
        - [1.1.1 Software](#111-software)
        - [1.1.2 Hardware](#112-hardware)
    - [1.2 Passwörter und Zugangsdaten](#12-passwörter-und-zugangsdaten)
    - [1.3 Remote Zugriff](#13-remote-zugriff)
        - [AnyDesk](#anydesk)
        - [TeamViewer](#teamviewer)
    - [1.4 Virtualisierung](#14-virtualisierung)
        - [VirtualBox](#virtualbox)
        - [Docker](#docker)
        - [WSL (Windows Subsystem für Linux)](#wsl-(windows-subsystem-für-linux))
        
- [2. Wichtige Befehle](wichtige%20befehle.md)
- [3. Setup](#3-setup)
    - [3.1 Host](#31-host)
        - [Windows 11 Home via Rufus](#windows-11-home-via-rufus)
        - [Benötigte Windows-Features](#windows-features)
    - [3.2 WSL](#32-wsl)
    - [3.3 Oracle VirtualBox](#33-oracle-virtualbox)
    - [3.4 nützliche Extensions für VS Code:](#34-nützliche-extensions-für-vs-code)
    - [3.5 Docker](#35-docker)
    - [3.6 Git](#36-git)
        - [Git Credentials konfigurieren](#git-credentials-konfigurieren)
- [4. Tests](#4-tests)
- [5. Docker Demo](#5-docker-demo)
- [6. Fehlerbehebungen](#6-fehlerbehebungen)
---

# 1. Übersicht
## 1.1 **Host**
(Höllenmaschine)
### 1.1.1 **Software**
- **Windows 11 Home** (unlizensiert)
### 1.1.2 **Hardware**
- **64 GB DDR4**
- **2TB M.2 NVMe SSD**

## 1.2 Passwörter und Zugangsdaten
### **Windows-User**
Username: `install`

Passwort: `azubilabor`

---
### **Ubuntu (WSL)**
Username: `weru`

Passwort: `weru`

---
### **Ubuntu (VirtualBox)**
Username: `weru`

Passwort: `weru`

---
### [**GitHub.com**](https://github.com/SandroFahrion-weru)


Username: `SandroFahrion-weru`

Mail: `sfa@dovista.com`

Passwort: `KroatienDummy900`

Access Token: `https://nextcloud.weru.de/s/t27TgMMkLb3r57L`

---
### **Hub.Docker.com**
(per GitHub Account)

Username: `sandrofahrionweru`

---
### **Nextcloud Server**
[nextcloud.local](http://nextcloud.local/)

Username: `admin`

Passwort: `weru`


---
### **ELK-Stack**
[kibana.local](http://kibana.local/)

## 1.3 **Remote Zugriff**
### **AnyDesk**

ID: `568433824`

Passwort: `wg.rem+tv`

### **TeamViewer**

ID: `1771198715`

Passwort: `wg.rem+tv`


## 1.4 **Virtualisierung**

### **VirtualBox**
- OpenSource (Personal Use and Educational License) 
- Für VMs 
- Detaillierte Dokumentation vorhanden (Betriebsanleitung mit 1256 Seiten)
- Unterstützung für RDP

### **Docker**

- Freie Nutzung (also ohne Lizenz produktiv nutzbar, jedoch nicht Docker Desktop)

### **WSL (Windows Subsystem für Linux)**
Installierte Distros:
- Ubuntu
- docker-desktop (automatisch von Docker Desktop erstellt)

---

# 3. Setup

## 3.1 Host
### **Windows 11 Home via Rufus**
[https://rufus.ie/de/](https://rufus.ie/de/)

### **In BIOS/UEFI**
- **Virtualisierungstechnologie aktivieren** (z.B. Intel Virtualization Technology)

### **Internetzugriff**
- Via LTE-Router

### **Grafik**
- Aktuelle Nvidia Studio Treiber installiert

### **Windows-Features**
Systemsteuerung -> Programme & Features -> "Windows Features aktivieren oder deaktivieren"
- Virtual Machine Platform
- Windows-Hypervisor-Plattform
- Windows-Subsystem für Linux

## 3.2 **WSL**
(**W**indows **S**ubsystem for **L**inux)
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

## 3.3 **Oracle VirtualBox**
### **Downloads**
[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads) 
- **Extension Pack**
- **User Guide**
- **Host App**

[https://www.oracle.com/virtualization/technologies/vm/downloads/virtualbox-downloads.html](https://www.oracle.com/virtualization/technologies/vm/downloads/virtualbox-downloads.html)
- **VirtualBox Guest Additions ISO**

#### Guest Additions installieren:
1. VM in VirtualBox starten
2. Im Fenstermenü unter **"Geräte"**
3. **"Optische Laufwerke"** und dann die `VBoxGuestAdditions.iso` auswählen
4. Alternativ: Direkt auf **"Gasterweiterungen einlegen..."**

### **Windows Server 2022**
- Evaluation Edition
- Desktop Experience
- 180 Tage Laufzeit, 3x verlängerbar (= 540 Tage)

#### Laufzeit verlängern:
In PowerShell:
   `slmgr.vbs /rearm`

## 3.4 **nützliche Extensions für VS Code:**
- Docker
- WSL
- YAML

## 3.5 Docker
[Docker Desktop - Installation für Windows](https://docs.docker.com/desktop/setup/install/windows-install/)

## 3.6 Git
### Installer für Git (64-Bit) herunterladen und ausführen
[Git für Windows: Downloads](https://git-scm.com/downloads/win)

---
### Git Credentials konfigurieren
In Powershell, Git CLI oder Bash:

    git config --global user.email "Email"
    git config --global user.name "Name"

Dementsprechend:

    git config --global user.email "sfa@dovista.com"                                      
    git config --global user.name "SandroFahrion-weru"

# 4. Tests

# 5. Docker Demo

# 6. Fehlerbehebungen
