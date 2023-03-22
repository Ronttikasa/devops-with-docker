### ex 1.1
```
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                      PORTS     NAMES
e9a1f019d8b8   nginx     "/docker-entrypoint.…"   57 seconds ago       Exited (0) 18 seconds ago             kind_wiles
c2880c06d3d9   nginx     "/docker-entrypoint.…"   About a minute ago   Exited (0) 10 seconds ago             frosty_lehmann
06c6c89b4642   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute           80/tcp    hardcore_williamson
```

### ex 1.2
```
$ sudo docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

$ sudo docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
```

### ex 1.3
```
docker run -d --rm -it --name secret devopsdockeruh/simple-web-service:ubuntu
docker exec -it secret bash
tail -f ./text.log
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

### ex 1.4
```
docker run -it --name search ubuntu sh -c 'echo "Input website:"; read website; echo "Searching..."; sleep 1; curl http://$website;'
docker exec -it search bash
apt-get -y update; apt-get -y install curl
```

### ex 1.5
the ubuntu version is significantly larger than the alpine; 83 MB vs 16 MB

to confirm secret message is the same:
```
docker run -dit --name secret devopsdockeruh/simple-web-service:alpine
docker exec -it secret sh
tail -f ./text.log
```

### ex 1.6
input: basics

answer: You found the correct password. Secret message is:
"This is the secret message"

### ex 1.7
Dockerfile:
```
FROM devopsdockeruh/simple-web-service:alpine

CMD server
```

```
docker build . -t web-server
docker run web-server
```

### ex 1.9
```
docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```

### ex 1.10
Added `EXPOSE 8080` to Dockerfile
```
docker run -p 8080:8080 simple-web-service
```

### ex 1.13
```
docker build . -t backend
docker run -p 127.0.0.1:8080:8080 backend
```

### ex 1.14
```
docker build . -t backend && docker run -p 127.0.0.1:8080:8080 backend
docker build . -t front && docker run -p 127.0.0.1:8000:5000 front
```

### ex 1.15
Dockerhub repo: https://hub.docker.com/repository/docker/ronttikasa/country-info/general

### ex 1.16
Deployed app: https://maiden-tiedot.fly.dev/

I set up a fly.io account, installed flyctl and ran `fly launch` in the app directory.
