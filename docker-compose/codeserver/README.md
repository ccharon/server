# Code Server Image aktualisieren
Mein erweitertes Image damit man mit dem code-server auch java entwickeln kann und paar andere Extras wie ein Chrome zur Anzeige "lokal" laufender Webanwendungen (per vscode Plugin)
Installieren update usw. ... in das Verzeichnis wechseln und folgendes ausführen.

## Container stoppen
```bash
sudo docker-compose stop
``` 

## das neue code-server image holen
```bash
sudo docker pull ghcr.io/linuxserver/code-server:latest
```

## das eigene Image neu bauen
```bash
sudo docker-compose build
``` 

## neu starten
```bash
sudo docker-compose up -d
``` 
