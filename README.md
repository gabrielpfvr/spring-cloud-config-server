Spring Cloud Config Server Application

Environment repo: https://github.com/gabrielpfvr/config-server-environment


To build the application run:

```
mvn clean package -DskipTests
```

Build docker image and start container:
```
docker build -t configserver .
docker run -d --name=configserver --restart=unless-stopped -p 8888:8888 -e API_TOKEN=yourtoken configserver
```

To encrypt keys:
```
curl localhost:8888/encrypt -s -d your_key
```

To access environment repository properties
```
curl localhost:8888/client-one/default -H "x-config-token: yourtoken"
```