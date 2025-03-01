# Polaris

## Tonton Jo  
### Join the community & Support my work   
[Click Here!](https://linktr.ee/tontonjo)  

## Sources:  
[Polaris github ](https://github.com/agersant/polaris)

## Usage:
Set rights on folder
```shell
mkdir -p /my/polaris/cache /my/polaris/data
chown -R 100:100 /my/polaris/cache /my/polaris/data
```

```shell
docker run -t -d \
  --name=polaris \
  --restart=unless-stopped \
  -p 5050:5050 \
  -v /my/music/directory:/music \
  -v /my/polaris/cache:/var/cache/polaris \
  -v /my/polaris/data:/var/lib/polaris \
  registry.gitlab.com/connectical/container/polaris
```
