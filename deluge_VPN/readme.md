# Deluge VPN

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  

## Usefull Links: 
[Github Deluge VPN](https://hub.docker.com/r/binhex/arch-delugevpn)  

## Other infos
[Express VPN affiliated Link](https://go.expressvpn.com/c/4824830/1509217/16063?sharedid=linktree)  

## Commands:
```shell
docker run -d \
    --cap-add=NET_ADMIN \
    -p 8112:8112 \
    -p 8118:8118 \
    -p 58846:58846 \
    -p 58946:58946 \
    --name=deluge-vpn \
    -v /sharedfolders/torrent:/data \
    -v /sharedfolders/dockerdata/deluge-vpn:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e VPN_ENABLED=yes \
    -e VPN_USER=username \
    -e VPN_PASS=password \
    -e VPN_PROV=custom \
    -e VPN_CLIENT=openvpn \
    -e STRICT_PORT_FORWARD=yes \
    -e ENABLE_PRIVOXY=yes \
    -e LAN_NETWORK=10.0.0.0/24 \
    -e NAME_SERVERS=209.222.18.222,84.200.69.80,37.235.1.174,1.1.1.1,209.222.18.218,37.235.1.177,84.200.70.40,1.0.0.1 \
    -e DELUGE_DAEMON_LOG_LEVEL=info \
    -e DELUGE_WEB_LOG_LEVEL=info \
    -e PUID=0 \
    -e PGID=0 \
    binhex/arch-delugevpn
```
