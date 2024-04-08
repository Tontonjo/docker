# Handbrake

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  

## Usefull Links: 
[Github Handbrake Jlesage](https://github.com/jlesage/docker-handbrake)  

## Other infos

## Commands:
### You may have to install git: in case of error "command not found"
```shell
docker run -d \
--name=handbrake \
-p 5800:5800 \
-v /PATH/dockerdata/handbrake:/config:rw \
-v /PATH/share/:/storage:ro \
-v /PATH/videos/handbrake/output:/output:rw \
-v /PATH/videos/handbrake/input:/watch:rw \
-e AUTOMATED_CONVERSION_FORMAT=mkv \
-e AUTOMATED_CONVERSION_PRESET=Matroska/tontonjo \
jlesage/handbrake
```
