# other

### Import .sql to container

```
$ docker exec -i containerid mysql -u’user’ -p’password’ database < dump.sql
```

### Set timezone

```
add apk — no-cache tzdata

RUN rm -f /etc/localtime && ln -s /usr/share/zoneinfo/Asia/Bangkok /etc/localtime
```