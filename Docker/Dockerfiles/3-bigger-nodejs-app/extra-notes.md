### Building an app with node_modules installed inside of a container doesn't work correctly. This is further explanation.

`$ docker run --init --rm --detatch -P anothername` This will run container in the background, but capital P is for exposing every port. Showing details with `$ docker ps` we will se specific port.
**Publish is a form of port mapping**

