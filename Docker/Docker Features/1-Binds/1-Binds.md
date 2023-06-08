Build it by `$ docker build` and then use **bind mouting**.
Before mouting, you can test this app by:\
`$ docker run -p myport:80 name-of-app` \
80 is a default port on nginx.

--------

`$ docker run --mount type=bind,source="$(pwd)"/build,target=/usr/share/nginx/html -p 8080:80 nginx` Tunneling content of a build folder into the container with a nginx.

----------
Little note - I don't know exactly if build folder is new folder for tunneling between a host and a container, or build folder should
be the whole root folder with an app. Issue - 403 error - forbidden.