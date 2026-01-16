## 👋 Welcome to ubuntu 🚀  

ubuntu README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update os ubuntu
```
  
## Install and run container
  
```shell
mkdir -p "/var/lib/srv/root/docker/casjaysdev/ubuntu/latest"
git clone "https://github.com/dockermgr/ubuntu" "$HOME/.local/share/CasjaysDev/dockermgr/ubuntu"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/ubuntu/dockerfs/." "/var/lib/srv/root/docker/casjaysdev/ubuntu/latest/"
docker run -d \
--restart always \
--privileged \
--name casjaysdev-ubuntu-latest \
--hostname ubuntu \
-e TZ=${TIMEZONE:-America/New_York} \
-v "/var/lib/srv/root/docker/casjaysdev/ubuntu/latest/data:/data:z" \
-v "/var/lib/srv/root/docker/casjaysdev/ubuntu/latest/config:/config:z" \
casjaysdev/ubuntu:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdev/ubuntu
    container_name: casjaysdev-ubuntu-latest
    environment:
      - TZ=America/New_York
      - HOSTNAME=ubuntu
    volumes:
      - "/var/lib/srv/root/docker/casjaysdev/ubuntu/latest/data:/data:z"
      - "/var/lib/srv/root/docker/casjaysdev/ubuntu/latest/config:/config:z"
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src os ubuntu
```
  
## Build container  
  
```shell
git clone "https://github.com/dockersrc/ubuntu" "$HOME/Projects/github/dockersrc/ubuntu"
cd "$HOME/Projects/github/dockersrc/ubuntu" && buildx all 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdev: [Github](https://github.com/dockersrc) [Docker](https://hub.docker.com/u/casjaysdev) ⛵  
