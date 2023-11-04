# Proxmox Backup Server 

## Tonton Jo - 2023

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
  -v /path/to/data/backup:/mnt/backup \
  -v /path/to/config/pbs/config/etc:/etc/proxmox-backup \
  -v /path/to/config/pbs/config/log:/var/log/proxmox-backup \
  -v /path/to/config/pbs/config/lib:/var/lib/proxmox-backup \
  --restart unless-stopped \
  ayufan/proxmox-backup-server:latest
```
## 2 - Login using PBS realm:
https://yourhost:8007  
admin:pbspbs
