# Installation und grundlegender Aufbau

## 1. Projektumgebung

Für dieses Projekt wurde eine virtuelle Serverumgebung mit VirtualBox eingerichtet.

Die Virtualisierung ermöglicht es, einen eigenständigen Linux-Server zu betreiben, ohne dafür einen separaten physischen Rechner zu benötigen.

**Verwendete Komponenten:**

| Komponente | Konfiguration |
|---|---|
| Virtualisierung | Oracle VirtualBox |
| Betriebssystem | Ubuntu Server 26.04.1 LTS |
| Arbeitsspeicher | 4 GB |
| Prozessor | 2 virtuelle CPU-Kerne |
| Festplatte | 30 GB |
| Netzwerkmodus | NAT |
| Hostname | ubuntu-server |

## 2. Installation und Grundeinrichtung

Nach der Installation von Ubuntu Server wurden die grundlegenden Systemeinstellungen vorgenommen.

Dazu gehören:

- Vergabe eines Hostnamens
- Einrichtung eines administrativen Benutzerkontos
- Einstellung der deutschen Zeitzone
- Aktualisierung der installierten Pakete
- Aktivierung automatischer Sicherheitsupdates

## 3. Netzwerk und Fernzugriff

Die virtuelle Maschine verwendet den NAT-Netzwerkmodus von VirtualBox.

Dadurch kann der Server ausgehende Netzwerkverbindungen aufbauen, während eingehende Verbindungen über eine eingerichtete Portweiterleitung gezielt ermöglicht werden.

Für die Administration wurde SSH eingerichtet.

Der Zugriff erfolgt über eine Portweiterleitung vom Windows-Host auf den SSH-Dienst der virtuellen Maschine. Die Anmeldung erfolgt mit einem SSH-Schlüsselpaar.

## 4. Docker und Containerverwaltung

Für den Betrieb der Monitoring-Komponenten wurde Docker installiert.

Zusätzlich kommt Docker Compose zum Einsatz. Damit können mehrere zusammengehörige Dienste zentral über eine Konfigurationsdatei verwaltet und gestartet werden.

Die Konfiguration der Monitoring-Umgebung befindet sich im Verzeichnis `monitoring/`.

## 5. Ergebnis

Es wurde eine funktionsfähige virtuelle Ubuntu-Serverumgebung eingerichtet, die als Grundlage für die weiteren Infrastruktur- und Monitoring-Komponenten dient.

Die Umgebung kann unabhängig vom Windows-Host administriert und schrittweise erweitert werden.
