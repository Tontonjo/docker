# Wireguard

[README](https://raw.githubusercontent.com/Tontonjo/docker/main/README.md)

## Usefull Links: 
[Docker Hub](https://github.com/linuxserver/docker-wireguard)  

```ssh
docker run -d \
  --name=wireguard \
  --cap-add=NET_ADMIN \
  --cap-add=SYS_MODULE \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -e SERVERURL=wireguard.domain.com `#set auto, fqdn or IP` \
  -e SERVERPORT=51820 `#optional` \
  -e PEERS=1 `#can be usernames as user1,user2` \ 
  -e PEERDNS=auto `#can define remote DNS like 10.0.0.1 and set search domain 10.0.0.1,local.domain.tld` \
  -e INTERNAL_SUBNET=10.13.13.0 `#optional` \
  -e ALLOWEDIPS=0.0.0.0/0 `# 0.0.0.0/0 means tunnel all - 10.0.0.0/24` \
  -e LOG_CONFS=true `#optional` \
  -p 51820:51820/udp \
  -v /path/to/appdata/config:/config \
  -v /lib/modules:/lib/modules \
  --sysctl="net.ipv4.conf.all.src_valid_mark=1" \
  --restart unless-stopped \
  lscr.io/linuxserver/wireguard
```
