`FROM node:13-stretch `

`USER node `

`RUN mkdir /home/node/code`

`WORKDIR /home/node/code` 


`COPY --chown=node:node package-lock.json package.json ./`\
it copies everything from package-lock and package, then runs npm ci.

`RUN npm ci`

`COPY --chown=node:node . .`\
For that reason, **it uses cash here** building layers, and RUN npm ci is not running as before\
`RUN npm ci` 

`CMD [ "node", "index.js" ]`

If nothing is change in package jsons but only in server files, then it will uses layers for packages, and will build completely new COPY step.