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