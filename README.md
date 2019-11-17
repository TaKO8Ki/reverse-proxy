# reverse-proxy

This proxy is based on [Traefik](https://github.com/containous/traefik).

## What is Traefik?

![traefik](https://user-images.githubusercontent.com/41065217/69004196-7ef25380-0952-11ea-84f6-e70c42c51dfe.png)

> Traefik is a modern HTTP reverse proxy and load balancer made to deploy microservices with ease.

## Usage

```sh
$ docker network create --driver=overlay --attachable proxy
```

Then, what you have to do is build containers in this network and set options.

If you need more information, please click the link below. 

https://docs.traefik.io/
