# Installation guide Defect Dojo + Remote PostgreSQL db connection

## Clean Docker Images, Container,...
```bash
docker rm -vf $(docker ps -aq)
docker rmi -f $(docker images -aq)
docker stop $(docker ps -a -q)
docker purge $(docker ps -a -q)
```
NB. Assicurarsi di aver rimosso tutto

## Install right version of docker-compose
```
sudo apt remove docker-compose-plugin
curl -s https://api.github.com/repos/docker/compose/releases/latest | grep browser_download_url  | grep docker-compose-linux-x86_64 | cut -d '"' -f 4 | wget -qi -
chmod +x docker-compose-linux-x86_64
sudo mv docker-compose-linux-x86_64 /usr/local/bin/docker-compose
docker-compose version
```

## Clone of repo
```bash
git clone https://github.com/DefectDojo/django-DefectDojo
cd django-DefectDojo
```

## Create database on postgresql
```
sudo -u postgres createdb <dbname-def>  # definitive db
sudo -u postgres createdb <dbname-test>  # test db
```

## Create user postgresql
```
sudo -u postgres createuser <username>
sudo -u postgres psql
alter user <username> with encrypted password '<password>';  # change password of user
grant all privileges on database <dbname> to <username> ;  # grant all privilege to user on specific table
```

## Edit env variables
1. Edit /docker/environments/postgres-redis.env
2. Edit dojo/settings/settings.dist.py (DD_DATABASE*)

## Build and Run
```bash
./dc-build.sh
./dc-up.sh postgres-redis
docker-compose logs initializer | grep "Admin password:"
```
