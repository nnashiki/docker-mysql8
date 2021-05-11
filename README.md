# docker-mysql8

init db

```
docker run --rm --name mysql8 \
    -d \
    --rm \
    -e MYSQL_ROOT_PASSWORD=baseball_pass \
    -e MYSQL_USER=baseball_user \
    -e MYSQL_PASSWORD=baseball_pass \
    -e MYSQL_DATABASE=baseball \
    -v `pwd`/mysql/db_init:/docker-entrypoint-initdb.d \
    -v `pwd`/mysql/cnf:/etc/mysql/conf.d \
    -p 3306:3306 mysql:8.0 
```

use db

```
mysql -u baseball_user -p -h 127.0.0.1
```
