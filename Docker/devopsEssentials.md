`docker container run --publish 80:80 nginx` 
Image is an application, container is a process of that application.
Left number is a host post.

`docker container run --publish 80:80 --detach nginx` Running in the background.

**Q:** What's the difference between docker container run vs docker container start?

`docker container rn --publish 80:80 --detach --name example nginx` ===> `docker container logs example` If it's running in the background and you need logs. ===> `docker container top example`  For showing processes inside.

`docker container rm -f numberid` rm is enough if it's not running.\
`docker rm $(docker ps -aq)` removing all containers\
`docker rmi $(docker images -q)` removing all images.\

-------
**Q:** What's the difference between docker container run -it vs docker container exec -it?

**app for -it flag is alwas after image**.

