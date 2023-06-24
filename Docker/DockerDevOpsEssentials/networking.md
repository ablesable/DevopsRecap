docker bridge network is also called "docker0".

`docker network ls` for showing all networks.\
`docker network inspect nameofnetwork` inspecting specific network in json format e.g. what containers are attached.

Docker host network attaches container directly to host interface.\
`docker network create nameofnetwork` creates new network with bridge driver.

`docker container run -d --name container name --network networkname imagename` adding new container to not default network.\

`docker network connect nameofnetwork nameofcontainer` adding a container to other network.

**Adding existing container to new network can add this container to 2 networks** One is bridge (default), second is newly specified.\
`docker (container) inspect nameofcontainer` for checking in json to what networks this is connected.

-----------

Docker containers use default DNS, and connection between them is done by this DNS service, cause ip addresses can change any moment.

`docker (container) exec -it nameofcontainer ping nameofnetwork` this can show other addresses any time we run this command. That's why DNS is working.

-------

--link flag is for linking between containers.