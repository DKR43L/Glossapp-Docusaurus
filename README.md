
# Dockerized Docusaurus Project

Dieses Projekt enthält verschiedene Komponenten für die Verwendung von Docusaurus in Docker-Containern. Es gibt drei Hauptverzeichnisse:

- `Dockerfiles`
- `dokugloss`
- `dokugloss_volume/_data`

## Dockerfiles

In diesem Ordner befinden sich zwei Dockerfiles für Docusaurus:

- **Dev Version**
- **Production Version**

### Dev Version

Diese Version ist für die Entwicklungsumgebung gedacht. Änderungen werden sofort gespeichert und angezeigt.

### Production Version

Diese Version ist für die Produktionsumgebung gedacht. Änderungen werden erst nach einem erneuten Build angezeigt.

### Docker Build & Run

Um die Docker-Images zu erstellen, können folgende Befehle verwendet werden:

```bash
docker build -t <image_name> .
```

Nach dem Erstellen des Images kann der Container mit folgendem Befehl ausgeführt werden:

```bash
docker run --rm -d -p 3000:6969 -v dokugloss_volume:/app/dokugloss <image_name>
```
Hinweis: Der Port `3000` kann beliebig gewählt werden, muss jedoch in der Dockerfile entsprechend angepasst werden.

Nachdem alles funktioniert hat kann die Seite unter der unterstehenden URL erreicht werden (Port kann abweichen):
http://localhost:3000 

## Verzeichnisstruktur

### dokugloss

Dieser Ordner enthält einen Docker-Container mit Docusaurus, der aus Docker exportiert und in das GitHub-Repository eingefügt wurde. Es ist ein normaler Docker-Container mit Docusaurus.

### dokugloss_volume/_data

Dieses Verzeichnis ist ein Volume, das sicherstellt, dass die Daten nach jedem Build erhalten bleiben und nicht gelöscht werden.

----------

## Unterschiede zwischen Dev und Production Version

### Dev Version

-   Änderungen werden nach dem speichern sofort angezeigt.

### Production Version

-   Änderungen werden erst nach einem erneuten Build angezeigt.

----------

## Zusammenfassung

Dieses Projekt ermöglicht eine einfache und flexible Verwendung von Docusaurus mit Docker. Durch die Trennung von Entwicklungs- und Produktionsumgebung können Änderungen effizient getestet und deployt werden. Das Volume sorgt dafür, dass Daten persistent gespeichert werden und nach jedem Build erhalten bleiben.
