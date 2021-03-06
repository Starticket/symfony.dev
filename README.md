# symfony.dev
Symfony on Docker

First, clone this repository:

```bash
$ git clone https://github.com/DjangoFR/symfony.dev.git
```

# Tools you need on your host

```text
docker
docker-compose ( min version >= 1.6)
  -> $ ./bin/docker-compose-install.sh
wget
mysql-client
phpstorm
  -> https://www.jetbrains.com/phpstorm/download/download-thanks.html?platform=linux
  or
  -> https://confluence.jetbrains.com/display/PhpStorm/PhpStorm+Early+Access+Program
```
---
# Add following to /etc/hosts
```bash
127.0.0.1	symfony.dev
```
---
# Installation (first time)

```bash
$ ./bin/dockremap.sh
$ ./bin/build.sh 
$ ./bin/start.sh 
$ ./bin/symfony.sh 
```
---
# Access your symfony.dev-Box
```
http://symfony.dev/app_dev.php/ 
```
---
# Updates
```bash
$ cd symfony.dev
$ git fetch origin master
$ git pull origin master

$ ./bin/stop.sh
$ ./bin/docker-delete-all-images.sh 
$ ./bin/build.sh 
$ ./bin/start.sh 
```
---
# Now you can start to

### connect to mysql

```bash
$ ./bin/mysql.sh
```

To connect to mysql from host (or db container) use:
```bash
mysql -uroot -p
```

To connect to mysql linked container (e.g. php-fpm):
```bash
mysql -h172.17.0.1 -uroot -p
```

### open TTY to one of containers

```bash
$ ./bin/tty.sh
```
and follow instructions.

### debug logs

```bash
$ tail -f ./logs/nginx/*
```

### debug in PhpStorm
[PhpStorm debugger configuration](doc/PHPSTORM.md)
