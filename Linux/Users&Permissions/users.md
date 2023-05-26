## Users and Logging
- logging of users is in the /etc/passwd file.
- Studying content of the file show us that our user, just logged into bash console on the begining. `user:x:1000:1000:,,,:/home/user:/bin/bash`
- <b>Principle of the least power:</b> A lot of functionalites of the linux system is logged on different accounts, because it helps the main user to have a lot of control. Some users are logged not into bash, and has NO POWER to access terminal.
- 