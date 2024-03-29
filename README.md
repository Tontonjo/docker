# docker
General docker informations and commands

## Tonton Jo  
### Join the community:
[![Youtube](https://badgen.net/badge/Youtube/Subscribe)](http://youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw?sub_confirmation=1)
[![Discord Tonton Jo](https://badgen.net/discord/members/h6UcpwfGuJ?label=Discord%20Tonton%20Jo%20&icon=discord)](https://discord.gg/h6UcpwfGuJ)
### Support my work, give a thanks and help the youtube channel:
[![Ko-Fi](https://badgen.net/badge/Buy%20me%20a%20Coffee/Link?icon=buymeacoffee)](https://ko-fi.com/tontonjo)
[![Infomaniak](https://badgen.net/badge/Infomaniak/Affiliated%20link?icon=K)](https://www.infomaniak.com/goto/fr/home?utm_term=6151f412daf35)
[![Express VPN](https://badgen.net/badge/Express%20VPN/Affiliated%20link?icon=K)](https://www.xvuslink.com/?a_fid=TontonJo)  
## Usefull Links: 
[Docker Hub](https://hub.docker.com/)  
[Linuxserver](https://fleet.linuxserver.io/)  
[Get docker](https://github.com/docker/docker-install)  

## Related video tutorials
[Watchtower - update containers automatically](https://www.youtube.com/watch?v=EqEA8W4lKpo)  
[Portainer - A docker web GUI](https://www.youtube.com/watch?v=ccHhQJUcO2U)  
[All my docker tutorials](https://www.youtube.com/playlist?list=PLU73OWQhDzsSyobL6E7McIGKYdR_hV6vR)  


## Install docker script (run as root or sudo):
```shell
wget -qO- https://get.docker.com/ | sh
```

## Usefull commands:
### Get docker general infos (docker root)
```shell
docker info
```
### Get infos about all containers
```shell
docker stats --all
```
### Get into a container
```shell
docker exec -it $containername bash
```
### Execute ping from a container directly
```shell
docker exec $containername ping 8.8.8.8
```
### Start a stopped container
```shell
docker start $containername
```
### Stop a started container
```shell
docker stop $containername
```
### Remove a stopped container
```shell
docker rm $containername
```
### Update a container
```shell
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once $containername
```
## Statistics:  
### Total RAM USED: 
source: https://stackoverflow.com/questions/47818470/compute-the-total-memory-used-by-docker-containers-in-bash
```shell
docker stats --no-stream --format 'table {{.MemUsage}}' | sed 's/\.\([0-9]*\)GiB/\1MiB/g' | sed 's/[A-Za-z]*//g' | awk '{sum += $1} END {print sum "MB"}'
```


