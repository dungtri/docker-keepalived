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
-e KEEPALIVED_EMAIL_FROM=keepalived@domain.com -e KEEPALIVED_EMAIL_TO=keepalived@domain.com \
-e KEEPALIVED_SMTP_SERVER=smtp2tg --restart=unless-stopped --net=host --privileged=true dungtri/keepalived
```

### Kubernetes
See [example](kubernetes.yaml)


## Travis
Note: if you clone this you need to set your travis env variables:

- `travis env set DOCKER_USER <your docker user>`
- `travis env set DOCKER_PASS <your docker password>`

