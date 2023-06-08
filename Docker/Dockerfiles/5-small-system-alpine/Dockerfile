FROM node:12-alpine

USER node 

RUN mkdir /home/node/code

WORKDIR /home/node/code 

COPY --chown=node:node package.json ./

RUN npm install 

COPY --chown=node:node . .

EXPOSE 3000

CMD [ "node", "index.js" ]