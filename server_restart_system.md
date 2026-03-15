# Server Restart System

This server uses a cron job + restart script + loop script to keep the server running automatically.

## Overview
cron (daily restart)
        ↓
restart.sh
        ↓
screen session
        ↓
start_server.sh
        ↓
run_server_x64.sh
        ↓
qzeroded

The loop script restarts the server if it crashes.

Cron forces a clean restart once per day.

## start_server.sh

This script runs the server in a loop so it automatically restarts if it crashes.
```
#!/bin/bash

cd /root/qlserver

while true
do
    ./run_server_x64.sh +exec server.cfg
    echo "Server stopped. Restarting in 5 seconds..."
    sleep 5
done
```
Start the server with:
```
screen -dmS qlserver /root/qlserver/start_server.sh
```

## restart.sh

This script safely restarts the server.

```
#!/bin/bash

pkill qzeroded
sleep 3

screen -S qlserver -X quit
sleep 2

screen -dmS qlserver /root/qlserver/start_server.sh
```

Cron Job

Check cron jobs:
```
crontab -l
```

Edit cron jobs:
```
crontab -e
```

Add this line after `crontab -e`:
```
0 5 * * * /root/qlserver/restart.sh
```

This restarts the server every day at 05:00.

Useful Commands

Check running screen sessions
```
screen -ls
```
Attach to server console
```
screen -r qlserver
```
Check ports
```
ss -ulpn | grep 279
```
Kill stuck servers

pkill qzeroded
