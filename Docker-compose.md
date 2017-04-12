# DOCKER COMPOSE

### Build/Re-build all

```
$ docker-compose build
```

### Build/Re-build Containers

```
$ docker-compose build {container-name}
```

### Which container to rebuild (change)

```
$ docker-compose up — no-deps -d web
```

### Close all running Containers

```
$ docker-compose stop
```

### To stop single container do:

```
$ docker-compose stop {container-name}
```

### Delete all existing Containers

```
$ docker-compose down
```

### Logs

```
$ docker-compose logs -f
```