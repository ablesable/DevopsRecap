`$ npm init -y`
`$ npm install @hapi/hapi hapi-pino`

-------

`COPY --chown=node:node . .` (everything what is going from a source directory goes to the specific directory in a container)

-------
`$ docker build -t my-bigger-node-app .`\
`$ docker run --init --rm --publish 3000:3000 my-bigger-node-app`
Everything is working, cause everything is installed on host coputer.

----------
`npm ci` will get everything in package-lock. It's quicker for dockerfile and containers.