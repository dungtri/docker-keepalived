# keepalived
[![Downloads](https://img.shields.io/docker/pulls/dungtri/keepalived.svg)](https://hub.docker.com/r/dungtri/keepalived/)
[![Build Status](https://travis-ci.org/dungtri/docker-keepalived.svg?branch=master)](https://travis-ci.org/dungtri/docker-keepalived)

Keepalived as docker container for [mutiple archs](https://hub.docker.com/r/angelnu/keepalived/tags):
- arm
- arm64
- amd64

## How to run
### Docker
```
docker run -d -e KEEPALIVED_PRIORITY=$priority -e KEEPALIVED_VIRTUAL_IP=$VIP -e KEEPALIVED_PASSWORD=$password \
--net=host --privileged=true angelnu/keepalived
```

### Swarm config with smtp2tg
```
version: '3.3'

services:
  smtp2tg:
    image: dungtri/smtp2tg
    ports:
      - 25:25
    deploy:
     mode: global
  keepalived-master:
    image: dungtri/keepalived
  keepalived-backup:
    image: dungtri/keepalived
    deploy:
     mode: global
```

### Kubernetes
See [example](kubernetes.yaml)


## Travis
Note: if you clone this you need to set your travis env variables:

- `travis env set DOCKER_USER <your docker user>`
- `travis env set DOCKER_PASS <your docker password>`

