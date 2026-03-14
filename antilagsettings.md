# Quake Live Antilag Presets

Antilag configuration presets for Quake Live servers.

These examples are provided in two formats:

`server.cfg` → for .cfg server configs

`XXXX.factories` → for factories / custom gamemode files

## Presets
- [Default / Conservative](#default--conservative)
- ["Best" #1](#best-1)
- ["Best" #2](#best-2)



## Default / Conservative

Lower rewind values. Favors low-ping players.

server.cfg
```
set g_lagHax "1"
set g_lagHaxMs "80"
set g_lagHaxMsec "10"
set g_lagHaxHistory "10"
```

XXXX.factories
```
"g_lagHax": "1",
"g_lagHaxMs": "80",
"g_lagHaxMsec": "10",
"g_lagHaxHistory": "10",
```

## "Best" #1

Balanced for servers with mixed regional players (≈60–200 ms)

server.cfg
```
set g_lagHax "1"
set g_lagHaxMs "240"
set g_lagHaxMsec "10"
set g_lagHaxHistory "12"
```

XXXX.factories
```
"g_lagHax": "1",
"g_lagHaxMs": "240",
"g_lagHaxMsec": "10",
"g_lagHaxHistory": "12",
```

## "Best" #2

Similar to #1, but with slightly higher rewind allowance.
 
server.cfg
```
set g_lagHax "1"
set g_lagHaxMs "250"
set g_lagHaxMsec "10"
set g_lagHaxHistory "12"
```

XXXX.factories
```
"g_lagHax": "1",
"g_lagHaxMs": "250",
"g_lagHaxMsec": "10",
"g_lagHaxHistory": "12",
```
