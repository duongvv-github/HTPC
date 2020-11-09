Installation Guide

Currently working on Ubuntu 20.04 minimal install of the desktop version.

## Basic linux install stuff:

```
sudo apt install curl
sudo apt install net-tools
```

### Client side:
run the three bash scripts in any order

TODO:
1. Kodi - automate various add ons and personal configuration
2. Retroarch - automate controller settings
3. Xpad driver to get xbox one controller working
4. Xpandneo (is this different from regular xpad?) to use bluetooth


### Docker setup (docker_basic) folder

1. docker_setup.sh

2. Run “id” under bash and setup environment variables in “sudo nano /etc/environment” with code:
```
PUID=${user_id}
PGID=${docker_id}
TZ="America/Los_Angeles"
USERDIR="/home/vincent"
MYSQL_ROOT_PASSWORD="passsword" # not using db for now
```
Then restart computer to re-set environ variables

3. docker_permissions.sh
Note: this is not the most secure version. Will need to revisit this later.

### Docker-compose

`mv `docker_compose.yml` to ~/docker/`
- unless changed the docker folder

Current pi-hole setup runs into issues with port 53 and clean Ubuntu install. This solves it.
```
sudo systemctl disable systemd-resolved.service
sudo systemctl stop systemd-resolved
```
Build docker image via
`docker-compose -f ~/docker/docker-compose.yml up -d`

view containers via `docker ps -a`

Access pihole via {local ip address}
Access organizr dash via {local ip address}:9980 (ip set in the docker compose)

### How to clear docker images

`docker stop $(docker ps -aq); docker rm $(docker ps -aq); docker rmi $(docker images -q);`
or
`docker system prune; docker image prune; docker volume prune;`

