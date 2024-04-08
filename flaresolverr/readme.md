# Flaresolverr

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  


## Usefull Links: 
[Flaresolverr Repository ](https://github.com/FlareSolverr/FlareSolverr)  

## Other infos

## Commands:
```shell
docker run -d \
  --name=flaresolverr \
  -p 8191:8191 \
  -e LOG_LEVEL=info \
  -e CAPTCHA_SOLVER=harvester \
  -e HARVESTER_ENDPOINT=https://127.0.0.1:5000/token \
  --restart unless-stopped \
  ghcr.io/flaresolverr/flaresolverr:latest
```
  
## Jackett:
```shell
docker run -d \
  --name=jackett \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Europe/London \
  -p 9117:9117 \
  -v <path to data>:/config \
  -v <path to blackhole>:/downloads \
  --restart unless-stopped \
  ghcr.io/linuxserver/jackett
```
