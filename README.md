# Ubuntu Server – Infrastruktur, Absicherung und Monitoring

## Projektbeschreibung

In diesem Projekt beschäftige ich mich mit dem Aufbau, der Absicherung und der Überwachung einer Linux-Serverinfrastruktur.

Ziel ist es, praktische Kenntnisse im Bereich Fachinformatik für Systemintegration zu erwerben und verschiedene Komponenten einer Serverumgebung miteinander zu verbinden.

Die Umgebung wurde mit Ubuntu Server in einer virtuellen Maschine unter VirtualBox eingerichtet. Für den Betrieb der Monitoring-Dienste kommt Docker Compose zum Einsatz.

## Technischer Aufbau

| Komponente | Aufgabe |
|---|---|
| Ubuntu Server 26.04 LTS | Betriebssystem der Serverumgebung |
| VirtualBox | Virtualisierung |
| Docker | Betrieb und Verwaltung der Container |
| Docker Compose | Verwaltung der Dienste |
| Prometheus | Erfassung und Speicherung von Metriken |
| Node Exporter | Bereitstellung von Systemmetriken |
| Grafana | Visualisierung der Messwerte |

### Architektur

- **Node Exporter** stellt Systeminformationen wie CPU-, Arbeitsspeicher-, Festplatten- und Netzwerkdaten bereit.
- **Prometheus** ruft diese Daten regelmäßig ab und speichert sie als Zeitreihen.
- **Grafana** greift auf Prometheus zu und stellt die Messwerte in einem Dashboard dar.

## Umgesetzte Sicherheitsmaßnahmen

Bei der Einrichtung wurde darauf geachtet, grundlegende Sicherheitsmaßnahmen umzusetzen:

- Firewall-Konfiguration mit UFW
- Standardmäßig eingehende Verbindungen blockieren
- SSH-Zugriff über Schlüsselauthentifizierung
- SSH-Passwortanmeldung deaktiviert
- Fail2Ban zum Schutz vor wiederholten fehlgeschlagenen Anmeldeversuchen
- Automatische Sicherheitsupdates mit Unattended Upgrades
- Monitoring-Dienste nur an die lokale Schnittstelle gebunden

## Monitoring

Mit Prometheus und Grafana wurde ein Dashboard zur Überwachung der Serverressourcen eingerichtet.

Aktuell werden folgende Bereiche überwacht:

- CPU-Auslastung
- Arbeitsspeicherauslastung
- Festplattennutzung
- Netzwerkverkehr

Die Messwerte werden regelmäßig erfasst und grafisch dargestellt.

## Projektstruktur

```text
ubuntu-server-infrastructure/
|-- monitoring/
|   |-- compose.yaml
|   `-- prometheus.yml
|-- documentation/
|-- screenshots/
|-- .gitignore
`-- README.md

## Projektstatus

Die grundlegende Serverinstallation, die Absicherung sowie die Einrichtung des Monitoring-Systems sind umgesetzt.

Das Projekt wird schrittweise erweitert. Die Dokumentation und weitere praktische Ergänzungen werden fortlaufend in diesem Repository gepflegt.

## Geplante Erweiterungen

- Monitoring und PromQL vertiefen
- Systemprotokollierung und Fehleranalyse
- Weitere Infrastruktur- und Sicherheitsfunktionen
- Erweiterung und Verbesserung der technischen Dokumentation

## Ziel des Projekts

Das Projekt dient dem eigenständigen praktischen Lernen im Rahmen meiner Umschulung zum Fachinformatiker für Systemintegration.

Dabei stehen der Umgang mit Linux-Servern, Netzwerktechnik, IT-Sicherheit, Virtualisierung und Monitoring im Mittelpunkt.

---

*Hinweis: Dies ist ein fortlaufendes Lern- und Praxisprojekt und keine produktive Unternehmensinfrastruktur.*
