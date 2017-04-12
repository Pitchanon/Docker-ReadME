# DOCKER SWARM

```
$ docker network create -d overlay mynet

$ docker service create — replicas 2 — name www-service — network mynet — publish 80:80/tcp www_server

$ docker node ls
$ docker service ls

```