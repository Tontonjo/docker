# Firefox Sync Server

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  

## Usefull Links: 
[Github Crazy-max Firefox Sync Server](https://github.com/crazy-max/docker-firefox-syncserver)  

## Other infos

## Commands:
Generate a random secret:
```shell
secret=$(LC_ALL=C tr -dc 'A-Za-z0-9!#%&\()*+,-./:;<=>?@[\]^_{}~' </dev/urandom | head -c 20) \
echo $secret
```  
Use this password to set FF_SYNCSERVER_SECRET in the docker run command:
```shell
 docker run -d \
    -p 5000:5000 \
	--name ffsyncserver \
	--restart unless-stopped \
    -e SYNCSERVER_PUBLIC_URL=http://yourdomain:5000 \
    -e SYNCSERVER_SECRET=<insertsecrethere> \
    -e SYNCSERVER_SQLURI=sqlite:////data/syncserver.db \
	  -v /path/to/data:/data \
    -e SYNCSERVER_BATCH_UPLOAD_ENABLED=true \
    -e SYNCSERVER_FORCE_WSGI_ENVIRON=false \
    -e SYNCSERVER_DEBUG_ENABLED=true \
    -e PORT=5000 \
	mozilla/syncserver:latest
  ``` 
## Firefox configuration:
enter this url in firefox: about:config  
Edit identity.sync.tokenserver.uri  
from: https://token.services.mozilla.com/1.0/sync/1.5  
to: http://fqdn.to.server:5000/token/1.0/sync/1.5

## Control:
```shell
docker logs -f ffsync
```  
try to start a sync  if nothing move:  
- Else you're all good
- Else your Firefox cant reach your server and you should control your network / DNS settings

if you get this error in log, ensure application URL match Public URL
```shell
ERROR:syncserver:The public_url setting doesn't match the application url.
This will almost certainly cause authentication failures!
    public_url setting is: http://localhost:5000
    application url is:    http://fqdn.to.server:5000
```
