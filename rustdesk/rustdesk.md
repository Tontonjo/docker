hbbs - RustDesk ID/Rendezvous server
hbbr - RustDesk relay server

```shell
docker run -d \
--restart unless-stopped \
--name hbbs \
--net=host \
-v /path/to/data/hbbs:/root \
rustdesk/rustdesk-server hbbs -r hbbrip:21117
```  
```shell
docker run -d \
--restart unless-stopped \
--name hbbr \
-v /path/to/data/hbbs:/root \
--net=host \
rustdesk/rustdesk-server hbbr
```
