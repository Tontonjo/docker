# Logitech Media Server - Squeezelite
## Start Container
https://hub.docker.com/r/lmscommunity/logitechmediaserver

```ssh
docker run -d \
      --name lms \
      --restart unless-stopped \
      -v /path/to/config:"/config":rw \
      -v  /path/to/music:"/music":ro \
      -v  /path/to/playlist:"/playlist":rw \
      -v "/etc/localtime":"/etc/localtime":ro \
      -v "/etc/timezone":"/etc/timezone":ro \
      -p 9000:9000/tcp \
      -p 9090:9090/tcp \
      -p 3483:3483/tcp \
      -p 3483:3483/udp \
      lmscommunity/logitechmediaserver
```
## Install LMS Client - Squeezlite
https://sourceforge.net/projects/lmsclients/files/squeezelite/linux/

```ssh
mkdir squeezelite
cd squeezelite
wget https://sourceforge.net/projects/lmsclients/files/squeezelite/linux/squeezelite-1.9.9.1401-armhf.tar.gz
tar -xzf squeezelite-1.9.9.1401-armhf.tar.gz
sudo mv squeezelite /usr/bin/squeezelite
squeezelite -l
```
```ssh
sudo nano /etc/systemd/system/squeezelite.service
```
```ssh
[Unit]

Description=Squeezelite

After=network.target
[Service]

ExecStart=/usr/bin/squeezelite -o hw:CARD=Headphones,DEV=0  -n player1 -s 10.0.0.171

[Install]

WantedBy=multi-user.target
```

```ssh
sudo systemctl enable squeezelite.service
sudo systemctl restart squeezelite.service
```
