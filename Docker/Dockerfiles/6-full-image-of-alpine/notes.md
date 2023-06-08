`$ docker inspect alpine:3.10 | jq` inspecting version of alpine 3.10 and colorize output. 

This container will be about 58mb.

----------
Because of the lack of the node layer and installing node & npm by\
`RUN apk add --update nodejs npm` , we have to add node user and node group by: \
`RUN addgroup -S node && adduser -S node -G node`