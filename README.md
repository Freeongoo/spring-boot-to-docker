# Simple move spring boot application to docker

1. create Dockerfile

```
FROM openjdk:11
RUN mkdir /demo
COPY target/demo-0.0.1-SNAPSHOT.jar /demo/demo-0.0.1-SNAPSHOT.jar
WORKDIR /demo
ENTRYPOINT ["java", "-jar", "demo-0.0.1-SNAPSHOT.jar"]
```

2. compile Dockerfile

`docker build -t demo .`

3. run docker 

`docker run -d --name demo -p 8080:8080 demo`

if need override custom port to passed SERVER_PORT

`docker run -d -e SERVER_PORT=8081 -p 8081:8081 demo`

4. connect to docker

`docker container exec -ti demo /bin/bash`