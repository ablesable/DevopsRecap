Build your container and then run:\
`$ docker run --env DATA_PATH=/data/num.txt --mount type=volume,src=incrementor-data,target=/data incrementor`

`env` flag is exposing the container to the DATA_PATH. Simply, Node.js knows where to write.\
`src` is a name of a volume.

----------

If data is only designed to be used and written to within Docker, then this makes **volumes** preferable and recommended by Docker.