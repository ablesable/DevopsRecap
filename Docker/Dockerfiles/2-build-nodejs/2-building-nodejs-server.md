`$ docker build -t my-name` -t flag is shorter version of --tag flag.

--------
`COPY` command in dockerfile copies content from one file to the another.

--------
After building and running container with this simple nodejs server, we are not able to connect.
**We should share the namespaces. To give network access to that container**
`$ docker run --init -rm --publish 3000:3000 my-name` This will get network from port 3000 in a container, and expose it on a 3000 port on a host machine.

--------
`$ docker run --init my-name` this wil run container with **tiny**, so ctrl + c will work on a container with node.js (Hack). Without this, SIGTERM should be used in an index.js file. Without it: `$ docker kill (process id)`.

--------
`USER` command in dockerfile creates specific user, to not run this on **root**.
Declaring a group by `--chown=user:group` is also important.

-------
After changing a user and a group we are allowed to `whoami` command.\
`$ docker run --init --rm --publish 3000:3000 my-app whoami`

-------
`WORKDIR` is a place where to put files copied in container.

`$ docker run --init --rm --publish 3000:3000 my-app pwd` will show a place where a file were copied, and we are in that direcotry in a new container.

-------
