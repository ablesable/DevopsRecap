## Users and Logging
- logging of users is in the /etc/passwd file.
- Studying content of the file show us that our user, just logged into bash console on the begining. `user:x:1000:1000:,,,:/home/user:/bin/bash`
- <b>Principle of the least power:</b> A lot of functionalites of the linux system is logged on different accounts, because it helps the main user to have a lot of control. Some users are logged not into bash, and has NO POWER to access terminal.

## Superuser
- sudo is a shortage of <b>S</b>uper<b>U</b>ser<b>DO</b>
- Sudo gives us a permission as root, and then we return to user we're currently logged in.
- `$ sudo su ` will switch users to root, and `$` will change to `#`.
- `# exit` will close root session.

## Creating new users
- Firstly we have to switch to root.
- `$ sudo useradd newuser`
- `$ sudo passwd newuser` helps to create a password for newuser
- `$ su newuser ` switch to new user, but right now newuser has not got any privileges.
- For giving a new user privileges we should use groups.
- Giving privileges: `$ sudo usermod -aG sudo newuser` (newuser added to usermod group, so now can use sudo).