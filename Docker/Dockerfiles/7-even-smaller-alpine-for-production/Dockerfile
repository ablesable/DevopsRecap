#BUILD STAGE

#first container just for building stuff
FROM node:12-stretch AS Build 
WORKDIR /build
#deleted chown, because in this scenario, just for building - this can be own by root.
COPY  package.json ./
RUN npm install 
COPY . .

## RUNTIME STAGE

FROM alpine:3.10
#updating nodejs, previously installed in Build Stage.
RUN apk add --update nodejs  
RUN addgroup -S node && adduser -S node -G node 
USER node 
RUN mkdir /home/node/code 
WORKDIR /home/node/code 
#copying the rest from the build stage. From /build to WORKDIR 
COPY --from=build --chown=node:node /build .

CMD ["node", "index.js"]