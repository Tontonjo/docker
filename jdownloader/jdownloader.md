# Jdownloader

## Tonton Jo - 2022

## Usefull Links: 
https://jdownloader.org/
https://hub.docker.com/r/jlesage/jdownloader-2

```ssh
docker run -d \
    --name=jdownloader \
    --restart unless-stopped \
    -p 5800:5800 \
    -v /path/to/jdownloader:/config:rw \
    -v /path/to/Downloads:/output:rw \
    jlesage/jdownloader-2
```
