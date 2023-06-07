`$ sudo docker run --interactive --tty (name of system/container)`\
This will run interactive pseudoterminal (tty) of a specific system.
**It pulls image, changes root, unshare from other env, and run specific cgroup**.

### Everything what I learned to this point is done by this command with the flags!

Alpine is a little linux distribution.
Closing container with `exit` command will close everything. Be careful with databases run on containers.\

`$ sudo docker run -it (name of a system/container)` (shorter way of --interactive --tty).

`$ sudo docker run (name of a system/container)` - this will only run a container in the background. The opposite what we wanted, cause after running that it **finishes and closes this container**.
The same situation is with this command, but with a specific command to what to do after running: e.g: 
`$ sudo docker run alpine:3.10 cat /etc/issue` will show version of that alpine and after that - closes terminal. 

-----------
`$ cat /etc/issue` will show the version of the system

-----------
`$ docker image prune` will clear the space.

-----------

`$ sudo docker run -it --detach (name of a system/container)` runs without closing but in the background (detach flag).

-----------
`$ docker kill (container id/name of container)` kills it like a process.

-----------
`$ sudo docker run -it --name (my own name) (name of a system/container)` It will run container with a specific name.

-----------


