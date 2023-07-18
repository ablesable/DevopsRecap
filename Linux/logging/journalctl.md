In the `/var/log/journal` will be persistant logs from `journald`. 
Logs from present session will be in `/run/log/journal`.

-------

`$ journalctl -b` will show every log from last booting. It is part of `systemd` deamon. 

----------
for rebooting wsl in cmd type: `wsl --shutdown`. Then `wsl` command will turn on this again.

-------
for persistant logging of every boot we need to go to the `/etc/systemd/journald.conf` file and change `#Storage=auto` to `#Storage=persistent`.

-----
For older logs type `$ journalctl --list-boots`. There will be all logs from previous bootings. Choose ID for looking into that log.
`$ journalctl -b (IDNumber)` or `$ journalctl -b (negative number)`

-------------
`$ journalctl --since ` is a flag for specific date we want to see logs.

--------
`$ journalctl -u (unitname)` for logs from specific unit. **For knowing which services are running type:**

```
systemctl --type=service --state=running
```

----------

More info [here](https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs)