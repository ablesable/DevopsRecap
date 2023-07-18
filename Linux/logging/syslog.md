Deamon which manages syslog service is `syslogd`.

----

Syslogd is older cousin of journald which is part of systemd. 

-----
Syslog service sends logs to the system logger.

For logging something `logger -s (something)`

-----

Syslog is writing logs in plain text. Main folder for them is in `/var/log/syslog`. In new linux systems, the newer version of syslogd deamon is `rsyslogd`. 

Logs from kernel are in `/var/log/dmesg`. **Available on a present boot.**

**Every info with kernel infor from dmesg is in**\
`/var/log/kern.log` . This is a file with **time**.

-----------

Configuration file is `/etc/rsyslog.d`\
In this file are also information of what logs are stored by syslogd.

------

**syslogd and journald are often running in the same time on the same system.**