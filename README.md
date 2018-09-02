# Docker LAMP
Quick start LAMP environment (Apache 2.4  MySQL 5.7 PHP 7.2 Memcached 1.5.7)

## Requirements
Docker and Docker-Compose should be installed
* [Docker ](https://docs.docker.com/install/) version 12 and above
* [Docker compose](https://docs.docker.com/compose/install/) version 1.10.0 and above

## Usage
* Copy your code to 'www' directory
* In docker-compose.yml file replace MYSQL_DATABASE, MYSQL_ROOT_PASSWORD, MYSQL_USER, MYSQL_PASSWORD with your own values
* To run the software, use:
```
docker-compose up -d
```
* ../db directory will contains your databases after creating
