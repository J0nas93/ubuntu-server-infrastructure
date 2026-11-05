# 1. Zielsetzung

Ein wichtiger Bestandteil des Projekts ist die Absicherung der Serverumgebung.

Ziel ist es, unberechtigte Zugriffe zu erschweren und grundlegende Sicherheitsmechanismen für den Betrieb eines Linux-Servers einzurichten.

# 2. Firewall mit UFW

Für die Verwaltung der Firewall wird UFW (Uncomplicated Firewall) verwendet.

Die grundlegende Konfiguration lautet:

- Eingehende Verbindungen werden standardmäßig blockiert.
- Ausgehende Verbindungen sind standardmäßig erlaubt.
- Der SSH-Port 22/TCP wurde für die Administration freigegeben.

Dadurch werden nur ausdrücklich erlaubte eingehende Verbindungen zugelassen.

# 3. SSH-Absicherung

Für die Fernadministration wird OpenSSH verwendet.

Die Anmeldung wurde mit einem SSH-Schlüsselpaar eingerichtet.

Folgende Einstellungen wurden umgesetzt:

- Anmeldung über öffentliche SSH-Schlüssel
- Deaktivierung der Passwortanmeldung
- Aktivierung der Public-Key-Authentifizierung
- Root-Anmeldung über SSH eingeschränkt

Der private SSH-Schlüssel verbleibt auf dem Windows-Host und wird nicht auf dem Server oder im GitHub-Repository veröffentlicht.

# 4. Schutz vor wiederholten Anmeldeversuchen mit Fail2Ban

Zusätzlich wurde Fail2Ban installiert und aktiviert.

Der Dienst überwacht fehlgeschlagene SSH-Anmeldeversuche.

Bei wiederholten fehlgeschlagenen Anmeldungen kann die betreffende IP-Adresse automatisch für einen festgelegten Zeitraum gesperrt werden.

Die SSH-Konfiguration wurde mit einem Funktionstest überprüft.

# 5. Automatische Sicherheitsupdates

Für die regelmäßige Installation von Sicherheitsaktualisierungen wird Unattended Upgrades verwendet.

Der Dienst wurde aktiviert, damit verfügbare Sicherheitsupdates automatisch installiert werden können.

# 6. Netzwerkzugriff auf Monitoring-Dienste

Die Weboberflächen von Prometheus und Grafana wurden so konfiguriert, dass sie ausschließlich an die lokale Schnittstelle des Servers gebunden sind.

Der Zugriff vom Windows-Host erfolgt über einen SSH-Tunnel.

Dadurch werden die Weboberflächen nicht direkt über die Netzwerkschnittstelle der virtuellen Maschine bereitgestellt.

# 7. Zusammenfassung

Durch die Kombination verschiedener Sicherheitsmaßnahmen wurde eine grundlegende Absicherung der Ubuntu-Serverumgebung umgesetzt.

Die Firewall begrenzt eingehende Netzwerkverbindungen, die SSH-Schlüsselanmeldung schützt den Fernzugriff und Fail2Ban erschwert wiederholte unberechtigte Anmeldeversuche. Automatische Sicherheitsupdates unterstützen außerdem die Aktualität des Systems.

Die Monitoring-Dienste sind nur lokal erreichbar und werden über einen SSH-Tunnel administriert.

Das Projekt vermittelt damit praktische Grundlagen zur Absicherung und Verwaltung eines Linux-Servers. Die Konfiguration stellt eine Lern- und Testumgebung dar und ist nicht als vollständig gehärtete Produktionsumgebung zu verstehen.
