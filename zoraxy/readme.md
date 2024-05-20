# Zoraxy

## Tonton Jo  
### Join the community & Support my work   
[Click Here!](https://linktr.ee/tontonjo)  

## Sources:  
[Zoraxy github ](https://github.com/tobychui/zoraxy)

## Usage:

```shell
docker run -d \
--name=zoraxy \
--restart=unless-stopped \
-p 8000:8000 \
-p 443:443 \
-p 80:80 \
-v /path/to/zoraxy:/opt/zoraxy/config/ \
zoraxydocker/zoraxy:latest
```
