# reverse-proxy

This proxy is based on [Traefik](https://github.com/containous/traefik).

## 📡 What is Traefik?

> Traefik is a modern HTTP reverse proxy and load balancer made to deploy microservices with ease.

<img src="https://user-images.githubusercontent.com/41065217/69004196-7ef25380-0952-11ea-84f6-e70c42c51dfe.png" width="300">

## 🚀 Usage

```sh
$ docker network create --driver=overlay --attachable proxy

$ docker stack deploy --compose-file docker-compose.yml [stack name]
```

e.g.
your service docker-compose.yml

```yml
services:
  web:
    deploy:
      labels:
        - traefik.frontend.rule=Host:www.${DOMAIN?Variable DOMAIN not set}
        - traefik.port=${PORT}
        - traefik.backend=puppeteer
        - traefik.docker.network=traefik-public
        - traefik.tags=traefik-public
        - traefik.enable=true
        - traefik.redirectorservice.frontend.entryPoints=http
        - traefik.redirectorservice.frontend.redirect.entryPoint=https
        - traefik.webservice.frontend.entryPoints=https
```

Then, what you have to do is build containers in this network and set options.

If you need more information, please click the link below. 

https://docs.traefik.io/
