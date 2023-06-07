`$ docker pull (name)` this will fetch and pull from registry the latest version of a specific container.

---------

`$ docker inspect node:12-stretch` this will give you a lot of information about a container. In this scenario node:12-stretch.

---------
`$ docker run -dit (name of a container)` shorter version of --detach flag and -it.

---------
`$ docker pause (id of a container)` frozing the container whatever it's doing in the moment.

---------
`$ docker unpause (id of a container)` unfrozing the container.

---------
`$ docker kill $(docker ps -q)` kills all docker containers that is running in the moment.

---------
`$ docker exec (name of a container/id of a container) command` this will find an existing container and try to execute something on that environment without closing it.

---------
`$ docker history (name of a container)` log with a history of a specific image/container.

---------
### For ssh connection to the cloud/host vm
`$ docker info ` Information about env that we connected to

---------
`$ docker top (id/name of a conteiner)` all processes that is going on specific container 

---------
`$ docker logs (id/name of a conteiner)` all logs from specific container 
