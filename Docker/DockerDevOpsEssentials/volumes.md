**`-e MYSQL_ALLOW_EMPTY_PASSWORD=True** is the way to turn mysql container on. Without env var it will not last long. 

-----------
`-v nameOfVolume:/var/lib/mysql` it will make a volume with specific **nameOfVolume** visible on `docker volume ls` command. **Additionaly** it will affect the name of a directory where /var/lib/mysql of a container will be mounted on a host. \
On a host it will not be listed in hash way, but the directory will be something like:\
` "Source": "/var/lib/docker/volumes/nameOfVolume/_data",` \
This will show after typing: `docker container inspect NameOfContainer`.

