# Deluge VPN

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  

## Usefull Links: 

## Other infos

## Commands:
### You may have to install git: in case of error "command not found"
```shell
apt-get install -y git
```
1: Copy, clone thoses files where you want them to be.
```shell
git clone https://github.com/Tontonjo/docker-nginx.git
```

2: Edit the files to match your domain / target environnement uncomment ssl settings if needed

3: start the container
```shell
docker run -d --name nginx --restart unless-stopped -v /target/path/nginx:/etc/nginx/ -p 80:80 -p 443:443 nginx
```
4: check logs: no output means everything looks fine
```shell
docker logs -f nginx
```

5:To reload conf without having to reboot container:
```shell
docker exec -it nginx /etc/init.d/nginx reload
```