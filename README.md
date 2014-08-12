## MySQL Dockerfile


This repository contains **Dockerfile** of [MySQL](http://dev.mysql.com/) for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/dockerfile/mysql/) published to the public [Docker Registry](https://index.docker.io/).


### Dependencies

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://index.docker.io/u/dockerfile/mysql/) from public [Docker Registry](https://index.docker.io/): `docker pull dockerfile/mysql`

   (alternatively, you can build an image from Dockerfile: `docker build -t="dockerfile/mysql" github.com/dockerfile/mysql`)


### Usage

#### Run `mysqld-safe`

    docker run -d --name mysql -p 3306:3306 dockerfile/mysql

#### Run `mysqld-safe` with persistent data directory.

    docker run -d -p 3306:3306 -v <data-dir>:/data --name mysql dockerfile/mysql

#### Run `mysql`

    docker run -it --rm --link mysql:mysql dockerfile/mysql bash -c 'mysql -h $MYSQL_PORT_3306_TCP_ADDR'
