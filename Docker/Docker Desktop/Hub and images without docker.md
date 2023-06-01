Docker hub has thousand containers. It's npm for containers. All these are free. \
`$ docker ps ` will show you all running containers. \
`$ docker pull mongo:3 ` is getting mongo 3 from docker hub.

Premade containers are called images. We can put containers on top of other containers (layers). Images are premade containers in some inherent state.

## E.G.
1. Running alpine docker container:
`# docker run -ti -v /var/run/docker.sock:/var/run/docker.sock --privileged --rm --name docker-host docker:18.06.1-ce`
2. On top of that, running alpine with shell in the background: 
 `# docker run --rm -dit --name my-alpine alpine:3.10 sh` 
3. Check what's running by:
 `# docker ps` 
4. Right now I can dump that two containers built on top of each other in one image by: 
 `# docker export -o nameofcontainer.tar name` 
5. By that in root file of a container, we have an image calle nameofcontainer.tar

6. Now we can **move that image to specifc directory** and by that make new root/new environment:
 `# tar xf nameofcontainer.tar -C specific-folder` \
 Going there will be new file system as in previous, more manual examples.
7. Now, familiar to us: `specific-folder # unshare --mount --uts --ipc --net --pid --fork --user --map-root-user chroot /specific-folder sh`
8. `# pwd` we are in root directory, and unshared previous namespaces.
9. mounting: \
    `# mount -t proc none /proc` \
    `# mount -t sysfs none /sys` \
    `# mount -t tmpfs none /tmp` 
10. 

