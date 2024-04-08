# Vaultwarden

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  

## Usefull Links: 
[Github Vaultwarden](https://github.com/dani-garcia/vaultwarden)

## Other infos
Dont forget that you need a [Reverse Proxy](https://www.youtube.com/watch?v=7nyn_kfBAjk)!  

## Commands:
```shell
docker run -d \
--restart unless-stopped \
--name vaultwarden \
-v /path/to/data:/data/ \
-p 80:80 \
vaultwarden/server:latest
```
