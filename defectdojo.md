# Installation guide Defect Dojo + Remote PostgreSQL db connection

## Clean Docker Images, Container,...
```bash
docker rm -vf $(docker ps -aq)
docker rmi -f $(docker images -aq)
docker stop $(docker ps -a -q)
docker stop $(docker ps -a -q)
```
NB. Assicurarsi di aver rimosso tutto

## Clone of repo
```bash
git clone https://github.com/DefectDojo/django-DefectDojo
cd django-DefectDojo
```

## Create database on postgresql
- Creare database definitivo
- Creare database di test

## Edit env variables
1. Edit /docker/environments/postgres-redis.env
2. Edit dojo/settings/settings.dist.py (DD_DATABASE*)

## Build and Run
```bash
./dc-build.sh
./dc-up.sh postgres-redis
docker-compose logs initializer | grep "Admin password:"
```
