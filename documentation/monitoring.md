# Monitoring mit Prometheus und Grafana

## 1. Zielsetzung

Ein wesentlicher Bestandteil des Projekts ist die Überwachung der virtuellen Ubuntu-Serverumgebung.

Ziel ist es, wichtige Systemressourcen kontinuierlich zu erfassen und übersichtlich darzustellen. Dadurch können Veränderungen der Systemauslastung erkannt und nachvollzogen werden.

Für die Umsetzung werden Prometheus, Node Exporter und Grafana eingesetzt.

## 2. Verwendete Komponenten

| Komponente | Aufgabe |
|---|---|
| Node Exporter | Erfasst Systemmetriken des Ubuntu Servers |
| Prometheus | Ruft Metriken regelmäßig ab und speichert diese |
| Grafana | Visualisiert die gespeicherten Messwerte |

Die Dienste werden über Docker Compose verwaltet.

## 3. Funktionsweise

Die einzelnen Komponenten arbeiten folgendermaßen zusammen:

1. Node Exporter stellt Informationen über den Zustand des Servers bereit.
2. Prometheus ruft diese Informationen in regelmäßigen Abständen ab.
3. Die erfassten Messwerte werden in Prometheus gespeichert.
4. Grafana greift auf Prometheus als Datenquelle zu.
5. Die Messwerte werden in einem Dashboard grafisch dargestellt.

Das konfigurierte Abrufintervall von Prometheus beträgt 15 Sekunden.

## 4. Überwachte Systemressourcen

Im Grafana-Dashboard werden aktuell folgende Bereiche dargestellt:

- **CPU-Auslastung:** Überwachung der Prozessoraktivität.
- **Arbeitsspeicher:** Darstellung der aktuellen RAM-Auslastung.
- **Festplattennutzung:** Überwachung des belegten Speicherplatzes.
- **Netzwerkverkehr:** Darstellung ein- und ausgehender Netzwerkdaten.

Die Visualisierung ermöglicht einen schnellen Überblick über die Ressourcennutzung des Servers.

## 5. Konfiguration und Zugriff

Die Konfiguration der Monitoring-Dienste befindet sich unter:

`/opt/monitoring/`

Dort liegen die Dateien:

- `compose.yaml`
- `prometheus.yml`

Prometheus und Grafana werden über Docker Compose gestartet und verwaltet.

Die Weboberflächen sind an die lokale Schnittstelle gebunden. Für den Zugriff vom Windows-Host wird ein SSH-Tunnel verwendet.

## 6. Hinweis zur Beispielkonfiguration

Die im Repository veröffentlichte Datei `prometheus.yml` enthält aus Datenschutzgründen einen Platzhalter für die IP-Adresse des Ubuntu Servers.

Vor der Verwendung muss `YOUR_UBUNTU_SERVER_IP` durch die tatsächliche IP-Adresse des eigenen Servers ersetzt werden.

Die auf der virtuellen Lernumgebung verwendete Originalkonfiguration bleibt davon unberührt.
