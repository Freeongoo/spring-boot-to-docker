# Simple move spring boot application to docker

1. create Dockerfile

2. compile Dockerfile

`docker build -t demo .`

3. run docker 

`docker run -d --name demo -p 8080:8080 demo`

if need override custom port to passed SERVER_PORT

`docker run -d -e SERVER_PORT=8081 -p 8081:8081 demo`

4. connect to docker

`docker container exec -ti demo /bin/bash`