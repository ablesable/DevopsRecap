`docker network create firstNetwork`\
`docker container run -d --name firstContainer --net firstNetwork --net-alias search elasticsearch:2`\
`docker container run -d --name secondContainer --net firstNetwork --net-alias search elasticsearch:2`\
`docker container run --rm --net firstNetwork alpine nslookup search`\
`docker container run --rm --net firstNetwork centos curl -s search:9200`\