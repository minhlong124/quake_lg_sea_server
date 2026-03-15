# SEA LG Duels Server

Custom configuration for a Vampiric LG (Shaft) duel practice server for Quake Live.

Designed for LG (Shaft) practice with fast rotations and minimal interruptions.

## Purpose

This project documents a working Quake Live LG duel server configuration originally designed for SEA players, but usable in any region.

## Features
- Designed for SEA duel practice
- Lightning Gun (Shaft) only
- Vampiric healing (100%)
- No knockback
- Thunderstruck map
- Voting disabled
- [Antilag tuned for ~40–200ms players](antilagsettings.md)

## Requirements

- Linux VPS
- [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD)
- Quake Live Dedicated Server
- GNU Screen
- Open UDP port: **27960**

Install the server using SteamCMD (standard process):

```
app_update 349090 validate
```

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

```
screen -S qlserver
./run_server_x64.sh +exec server.cfg
```
Detach with:
```
CTRL+A → D
```
## Reconnect to Server Console
```
screen -ls
screen -r <session>
```
## Example Connect Command
```
/connect (server-ip):27960
```


## Notes

- This configuration is intended for Thunderstruck duel rotations where players queue and rotate after each fight.
- For Windows-based servers, see [this setup guide.](https://steamcommunity.com/sharedfiles/filedetails/?id=1410490276)
