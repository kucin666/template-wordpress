## BACKUP DATA WORDPRESS MYSQL DARI DOCKER CONTAINER
- cek docker container & copy id container mysql
```
docker ps -a
```
```
$ docker ps -a
CONTAINER ID   IMAGE              COMMAND                  CREATED          STATUS          PORTS                                   NAMES
e5888b6f3b5e   wordpress:latest   "docker-entrypoint.s…"   53 minutes ago   Up 53 minutes   0.0.0.0:8000->80/tcp, :::8000->80/tcp   template-wordpress-wordpress-1
06adc68fee18   mysql:5.7          "docker-entrypoint.s…"   53 minutes ago   Up 53 minutes   3306/tcp, 33060/tcp                     template-wordpress-db-1
```

- masuk ke docker container mysql
```
docker exec -it 06adc68fee18 /bin/bash
```
- backup
```
mysqldump -u wordpress -p wordpress --no-tablespaces > wordpress666.sql
```
- exit
```
exit
```
- copy file sql ke folder lokal
```
docker cp 06adc68fee18:wordpress666.sql /workspace/template-wordpress/
```
DONE