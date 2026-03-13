# SEA LG Duels Server

Custom configuration for a Vampiric LG / Shaft duel practice server for Quake Live.

Designed for LG / Shaft practice with fast rotations and minimal interruptions.



## Features

- Lightning Gun / Shaft only
- Vampiric healing (100%)
- No knockback
- Thunderstruck map
- Antilag tuned for ~40–200ms players
- Voting disabled
- Designed for SEA duel practice

## Requirements

- Linux VPS
- SteamCMD
- Quake Live Dedicated Server

## Directory Structure

```
qlserver/
└─ baseq3/
   ├─ server.cfg
   └─ scripts/
      ├─ factories.txt
      └─ lgvamp.factories
```

## Starting the Server

Run the server inside a screen session:

screen -S qlserver
./run_server_x64.sh +exec server.cfg

Detach with:

CTRL+A → D

## Reconnect to Server Console

screen -ls
screen -r <session>

## Example Connect Command

/connect (server-ip):27960

## Notes

This configuration is intended for Thunderstruck duel rotations where players queue and rotate after each fight.
