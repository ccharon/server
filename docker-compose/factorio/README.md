# Factorio

## damit es geht braucht man einen factorio user der auch Zugriff auf das Verzeichnis /opt/factorio hat 
```bash
useradd -u 845 -g 845 factorio
mkdir -p /opt/factorio
chown 845:845 -R /opt/factorio
```
## Einstellungen für das Spiel
interessant ist hier das Verzeichnis /opt/factorio/config/

Ein paar Dateien bestimmen wie karten generiert werden und so map-gen-settings.json und map-settings.json

### server-adminlist.json
```
[
"username"
]
```
### server-whitelist.json 
```
[
"username"
]
```
### rconpw
```
passwortplaintext
```
### server-settings.json (Auszüge)
```
...
 "visibility":
  {
    "public": false,
    "lan": false
  },
  
  "_comment_credentials": "Your factorio.com login credentials. Required for games with visibility public",
  "username": "",
  "password": "",

  "_comment_token": "Authentication token. May be used instead of 'password' above.",
  "token": "token setzen ... wo gab es den nur her ... ich glaub auf der seite, braucht man um plugins zu laden und so",

  "game_password": "eigenes passwort",

  "_comment_require_user_verification": "When set to true, the server will only allow clients that have a valid Factorio.com account",
  "require_user_verification": true,
...
```
