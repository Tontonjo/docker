# Proxmox Backup Server 

## Tonton Jo - 2022

## Usefull Links: 
[Ayufan Repository ](https://github.com/ayufan/pve-backup-server-dockerfiles)  
[Commandes utiles docker](https://raw.githubusercontent.com/Tontonjo/docker/main/README.md)  

## 1 - Start the container
```ssh
docker run -d \
  --name=pbs \
  --network=host \
  --tmpfs=/run \
  -e TZ=Europe/Zurich \
  -h pbs \
  -v /sharedfolders/dockerdata/lab/pbs/backup:/mnt/backup \
  -v /sharedfolders/dockerdata/lab/pbs/config/etc:/etc/proxmox-backup \
  -v /sharedfolders/dockerdata/lab/pbs/config/log:/var/log/proxmox-backup \
  -v /sharedfolders/dockerdata/lab/pbs/config/lib:/var/lib/proxmox-backup \
  --restart unless-stopped \
  ayufan/proxmox-backup-server:latest
```
## 2 - Login using PBS realm:
admin:pbspbs

## 2 - Change the password:
```ssh
docker exec -it pbs passwd
```
