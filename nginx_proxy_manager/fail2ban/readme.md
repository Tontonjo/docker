# Fail2ban in Nginx Proxy Manager

## Tonton Jo  
### Join the community:
[![Youtube](https://badgen.net/badge/Youtube/Subscribe)](http://youtube.com/channel/UCnED3K6K5FDUp-x_8rwpsZw?sub_confirmation=1)
[![Discord Tonton Jo](https://badgen.net/discord/members/h6UcpwfGuJ?label=Discord%20Tonton%20Jo%20&icon=discord)](https://discord.gg/h6UcpwfGuJ)
### Support my work, give a thanks and help the youtube channel:
[Link-tree](https://linktr.ee/tontonjo)  
## Sources:  
https://nginxproxymanager.com/  
https://github.com/NginxProxyManager/nginx-proxy-manager/issues/39  
https://forum.openmediavault.org/index.php?thread/49562-nginx-proxy-manager-with-fail2ban-guide/  
https://gist.github.com/Rankarusu/23a04ed587b05c6f2b701f2457a127b0  


## Installation OUT of container (on host)
#### Install fail2ban
```ssh
apt-get update && apt-get install -y fail2ban nano
```
Copy my fail2ban configurations in respective folders action.d, jail.d and filter.d
- Use npm.local in /etc/fail2ban/jail.d/
- Edit path to match your environement

#### Set fail2ban service dependency to wait for docker (necessary to ensure fail2ban rules get in first position)
!! this probably has to be done every major update !!
Add docker.service to fail2ban.service configuration
```ssh
nano /usr/lib/systemd/system/fail2ban.service
```
```ssh
After=network.target iptables.service firewalld.service ip6tables.service ipset.service nftables.service docker.service
```
If you dont want to deal with the fail2ban service for any reason, you can add a delay to the action.d file
```ssh
actionstart = sleep 30
              iptables -N f2b-npm-docker
              iptables -A f2b-npm-docker -j RETURN
              iptables -I FORWARD -p tcp -m multiport --dports 0:65535 -j f2b-npm-docker
```


## Installation IN container
####  Preparation
In order to have a reliable fail2ban configurations some adaptations to your container are needed.
- If you recreate the container (changes to container settings) you'll have to reinstall fail2ban manually. Configurations will be retained if you follow my advices here.
- I'd suggest you to remove npm from being automatically updated

Edit your container configuration to set the following:

- Enable the net_admin capability in your container
- Add the following folders mapping to save configurations
```ssh
/path/to/npm/fail2ban:/etc/fail2ban
/path/to/npm/fail2ban/database:/var/lib/fail2ban
```

Log into your Nginx proxy manager container:
```ssh
docker exec -it $nginxproxymanagercontainer bash
```
Install fail2ban
```ssh
apt-get update && apt-get install -y fail2ban nano
```
- Your folder /path/to/npm/fail2ban should now contain all default jails
disable ssh default jail as it is useless by setting sshd jail to false
```ssh
nano /etc/fail2ban/jail.d/defaults-debian.conf
```
```ssh
[sshd]
enabled = false
```
Copy my fail2ban configurations in respective folders jail.d and filter.d
- Use npm-docker.local in /etc/fail2ban/jail.d/

Start the service:
```ssh
service fail2ban start
```
Ensure the service will start with a container reboot: add service start in init
```ssh
nano /init
```
```ssh
service fail2ban start
```
## Test!
Use the following management commands to ban yourself:
- check that your NPM services are not accessible anymore
- Reboot your server and ensure they are still not accessible :)

## Management
### List jails
```ssh
fail2ban-client status
```
### List jails details
```ssh
fail2ban-client status npm-docker
```
### Ban an IP
```ssh
fail2ban-client set npm-docker banip $anip
```
### Unban an IP
```ssh
fail2ban-client set npm-docker unbanip $anip
```
### Find when an IP was banned and infos about it
```ssh
sqlite3 -header -column 'file:/var/lib/fail2ban/fail2ban.sqlite3?mode=ro' "select * from bans where jail='npm-docker' AND ip='$ipaddress' order by timeofban desc limit 10"
```

## Debugging:
### Fail2ban Regex
You can test your regex against actual logs or sample ones with this command:
```ssh
fail2ban-regex "/path/to/log.txt" "/etc/fail2ban/filter.d/npm-docker.conf" --print-all-matched
```
### If an ip got banned by mistake you can try to identify why by obtaining a list of the lines containing IP's
```ssh
grep $IPADDRESS "/path/to/logs/*.log" > log.txt
```
### If the case is old you can look into archives
```ssh
zgrep $IPADDRESS "/path/to/logs/*.gz" > log.txt
```
