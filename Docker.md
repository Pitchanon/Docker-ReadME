# Docker

### แสดง container ที่ทำงานอยู่

```
$ docker ps
```
### แสดง image ที่มีอยู่

```
$ docker images
```

### BUILD

```
$ docker build -t ${IMAGE}:${VERSION} .
$ docker build -t pitchanon/example:1.0 .
$ docker build -t pitchanon/example:1.0 -t pitchanon/example .
```

### TAG

```
$ docker tag -f ${IMAGE}:${VERSION} ${IMAGE}:latest
```

### RUN

```
$ docker run -d -p 80:80 — name myprofile pitchanon/example-profile

$ docker run — name hellomobydock -v ~/web:/usr/share/nginx/html:ro -p 80:80 -d nginx:1.9
```

- `-v` แบ่งด้วย : ด้านซ้ายคือ path ในเครื่องของเรา และด้านขวาคือ path ใน Container
- `-p` 80:80 ใช้งาน port 80 บน Linux เมื่อไหร่ให้ทะลุไปทำงานยัง Container นี้ที่ port 80
- `-d` ทำงานในเบื่องหลัง


###  PULL

```
$ docker pull nginx:1.9
```

### PUSH

```
$ docker push nginx:1.9
```

### DEBUG

```
$ docker exec -it ${IMAGE} bash
```

### COMMIT

```
$ docker commit -m “First Commit” -a “Pitchanon” ea534014a41f eon01/vote:v1

```
ea534014a41f — Container ID

## REMOVE
### Remove image

```
$ docker rmi -f image_name
```

### Remove container

```
$ docker rm -f containner_name
```

### Delete all stopped containers

```
$ docker rm $( docker ps -q -f status=exited)
```

### Delete all dangling (unused) images

```
$ docker rmi $( docker images -q -f dangling=true)
$ docker rmi -f $(docker images | grep ‘172.16.20.223’ | awk {‘print $3’})
```

### Delete ALL images

```
$ docker rmi $(docker images -q)
```

### Using docker-gc for clean

```
$ docker run — rm -v /var/run/docker.sock:/var/run/docker.sock -v /etc:/etc spotify/docker-gc
```

### LOG

```
$ docker logs -tf container_name
```

### COPY FILE FROM CONTAINER

```
$ docker cp container:/path/to/file file
```

### SSH bash เข้าไปที่เครื่อง Container (เหมือน SSH เข้าไป)

```
$ docker exec -it CONTAINER_ID bash
```

### ดูรายละเอียดของแต่ละ Container ที่กำลังรันอยู่

```
$ docker stats

$ docker stats --format "table {{.Container}}\t{{.CPUPerc}}\t{{.MemUsage}}\t{{.MemPerc}}\t{{.NetIO}}\t{{.BlockIO}}\t{{.Name}}"
```