# Minecraft als Dockerimage
## aktualisieren
zum aktualisiern in das Verzeichnis mit der docker-compose.yaml gehn
```
sudo docker-compose stop
sudo docker-compose pull
sudo docker-compose up -d
```
## damit es geht braucht man einen minecraft user der auch Zugriff auf das Verzeichnis /opt/minecraft hat 
```bash
useradd -u 999 -g 993 minecraft
mkdir -p /opt/minecraft
chown 999:993 -R /opt/minecraft
```
## im /opt/minecraft Verzeichnis braucht es ein paar Einstellungen
### whitelist.json (sicherstellen das nur erlaubte User einloggen können
```
[
  {
    "uuid": "<meine minecraft account uuid>",
    "name": "<meine minecraft account name>"
  }
]
```
### ops.json (admin und so)
```
[
  {
    "uuid": "<meine minecraft account uuid>",
    "name": "<meine minecraft account name>"
    "level": 4,
    "bypassesPlayerLimit": true
  }
]
```
### server.properties
```
#Minecraft server properties
#Tue Apr 06 13:58:26 GMT 2021
spawn-protection=0
max-tick-time=60000
query.port=25565
generator-settings=
sync-chunk-writes=true
force-gamemode=false
allow-nether=true
enforce-whitelist=true
gamemode=survival
broadcast-console-to-ops=true
enable-query=false
player-idle-timeout=0
text-filtering-config=
difficulty=normal
spawn-monsters=true
broadcast-rcon-to-ops=true
op-permission-level=4
pvp=true
entity-broadcast-range-percentage=100
snooper-enabled=true
level-type=default
hardcore=false
enable-status=true
enable-command-block=true
max-players=20
network-compression-threshold=256
resource-pack-sha1=
max-world-size=29999984
function-permission-level=2
rcon.port=25575
server-port=25565
texture-pack=
server-ip=
spawn-npcs=true
allow-flight=false
level-name=Fhloston Paradise
view-distance=16
resource-pack=
spawn-animals=true
white-list=true
rcon.password=minecraft
generate-structures=true
max-build-height=256
online-mode=true
level-seed=-562179930
prevent-proxy-connections=false
use-native-transport=true
enable-jmx-monitoring=false
enable-rcon=true
motd=just another day in paradise
rate-limit=0
```
