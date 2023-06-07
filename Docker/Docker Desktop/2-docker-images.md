`$ sudo docker run --interactive --tty (name of system/container)`\
This will run interactive pseudoterminal (tty) of a specific system.
**It pulls image, changes root, unshare from other env, and run specific cgroup**.

### Everything what I learned to this point is done by this command with the flags!

Alpine is a little linux distribution.
Closing container with `exit` command will close everything. Be careful with databases run on containers.\

`$ sudo docker run -it (name of a system/container)` (shorter way of --interactive --tty).

`$ sudo docker run (name of a system/container)` - this will only run a container in the background. The opposite what we want.
