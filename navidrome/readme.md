# Navidrome

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  

## Usefull Links: 
[Github Navidrome](https://github.com/navidrome/navidrome/)  

## Other infos

## Commands:
### You may have to install git: in case of error "command not found"
```shell
docker run -d \
--name navidrome \
--restart=unless-stopped \
-v /path/to/music:/music \
-v /path/to/data:/data \
-p 4533:4533 \
deluan/navidrome:latest
```
