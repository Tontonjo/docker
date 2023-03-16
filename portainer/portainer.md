# Tonton Jo - 2021
Join me on Youtube: https://www.youtube.com/c/TontonJo

## Sources
https://docs.portainer.io/start/install-ce/server/docker/linux

# All containers, purge, at defined time
```ssh
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```
