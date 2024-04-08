# Nativefier

## Tonton Jo
[Social links](https://linktr.ee/tontonjo)  

## Usefull Links: 
[Github Nativefier](https://github.com/nativefier/nativefier  )  

## Other infos

## Commands:
### Create Windows app from a website:
```shell
docker run --rm -v /path/to/docker/nativefier/apps/:/target/ nativefier/nativefier -p windows https://url /target/  
```
### Create Windows app from a website with firefox agent:
```shell
docker run --rm -v /path/to/docker/nativefier/apps/:/target/ nativefier/nativefier -p windows --user-agent firefox https://url /target/  
```
### Create Windows app from a website with custom Icon:
```shell
docker run --rm -v /path/to/docker/nativefier/apps/:/target/ nativefier/nativefier -p windows --icon /target/jo.jpg --user-agent firefox https://url /target/  
```
### Create Windows app from a website with custom name:
```shell
docker run --rm -v /path/to/docker/nativefier/apps/:/target/ nativefier/nativefier -p windows --name testexe --user-agent firefox https://url /target/  
```
### Create Windows app from a website and disable old build warning (yeah, it's insecure)
```shell
docker run --rm -v /path/to/docker/nativefier/apps/:/target/ nativefier/nativefier --disable-old-build-warning-yesiknowitisinsecure -p windows --user-agent firefox https://url /target/  
```

## Controls in app:
### Show menu bar
ctrl
### Reload page
ctrl + r  
