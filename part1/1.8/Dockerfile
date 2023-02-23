FROM ubuntu:20.04

WORKDIR /usr/src/app

RUN apt-get -y update; apt-get -y install curl

COPY web-search.sh .

RUN chmod +x web-search.sh

ENTRYPOINT [ "./web-search.sh" ]
