# docker
General docker informations and commands

## Tonton Jo - 2021  
### Join the community:
[![Youtube channel](https://github-readme-youtube-stats.herokuapp.com/subscribers/index.php?id=UCnED3K6K5FDUp-x_8rwpsZw&key=AIzaSyA3ivqywNPQz0xFZBHfPDKzh1jFH5qGD_g)](http://youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw?sub_confirmation=1)
[![Discord Tonton Jo](https://badgen.net/discord/members/2NQskxZjfp?label=Discord%20Tonton%20Jo,%20&icon=discord)](https://discord.gg/2NQskxZjfp)
### Support the channel with one of the following link:
[![Ko-Fi](https://badgen.net/badge/Buy%20me%20a%20Coffee/Link?icon=buymeacoffee)](https://ko-fi.com/tontonjo)
[![Infomaniak](https://badgen.net/badge/Infomaniak/Affiliated%20link?icon=K)](https://www.infomaniak.com/goto/fr/home?utm_term=6151f412daf35)
[![Express VPN](https://badgen.net/badge/Express%20VPN/Affiliated%20link?icon=K)](https://www.xvuslink.com/?a_fid=TontonJo)  

## Usefull Links: 
[Docker Hub](https://hub.docker.com/)
[Linuxserver](https://fleet.linuxserver.io/)
[Get docker](https://github.com/docker/docker-install)  

## Install docker script:
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

