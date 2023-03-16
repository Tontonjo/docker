# Tonton Jo - 2021
Join me on Youtube: https://www.youtube.com/c/TontonJo

## Sources
https://github.com/containrrr/watchtower
 https://containrrr.dev/watchtower/

## list of arguments: 
 https://containrrr.dev/watchtower/arguments/
 https://github.com/containrrr/watchtower

## All containers, purge, at defined time
docker run -d \
    --name watchtower \
    --restart=unless-stopped \
    -e WATCHTOWER_SCHEDULE="0 0 4 * * *" \
    -e WATCHTOWER_CLEANUP="true" \
    -e TZ="Europe/paris" \
    -v /var/run/docker.sock:/var/run/docker.sock \
    containrrr/watchtower
    
## only the specified container, purge, at defined time
docker run -d \
    --name watchtower2 \
    --restart=unless-stopped \
    -e WATCHTOWER_SCHEDULE="0 0 4 * * *" \
    -e WATCHTOWER_CLEANUP="true" \
    -e TZ="Europe/paris" \
    -v /var/run/docker.sock:/var/run/docker.sock \
    containrrr/watchtower \
    containername1 containername2 containername3
    
## only the containers with include tag, purge, at defined time - add label "com.centurylinklabs.watchtower.enable" to "true" on containers
docker run -d \
    --name watchtower \
    --restart=unless-stopped \
    -e WATCHTOWER_SCHEDULE="0 0 4 * * *" \
    -e WATCHTOWER_CLEANUP="true" \
    -e WATCHTOWER_LABEL_ENABLE="true" \
    -e TZ="Europe/paris" \
    -v /var/run/docker.sock:/var/run/docker.sock \
    containrrr/watchtower
