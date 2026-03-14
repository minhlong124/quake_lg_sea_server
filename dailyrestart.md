# Automatic Daily Restart (Recommended)

Some Quake Live servers may eventually run into a bug where the server starts using 100% of one CPU core, even when no one is playing.

This tends to happen after the server has been running for a long time.

A simple way to avoid it is to restart the server once every 24 hours.

## Example cron configuration:

```
crontab -e
```

Add the following lines:
```
0 5 * * * screen -S qlserver -X quit
1 5 * * * screen -dmS qlserver ~/qlserver/run_server_x64.sh +exec server.cfg
```

This will:
- stop the running server at 05:00
- start a fresh instance at 05:01

This helps prevent the long-running CPU usage issue.
