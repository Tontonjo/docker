docker run -it \
      --name lms \
      --restart unless-stopped \
      -v /path/to/config:"/config":rw \
      -v  /path/to/music:"/music":ro \
      -v  /path/to/playlist:"/playlist":rw \
      -v "/etc/localtime":"/etc/localtime":ro \
      -v "/etc/timezone":"/etc/timezone":ro \
      -p 9000:9000/tcp \
      -p 9090:9090/tcp \
      -p 3483:3483/tcp \
      -p 3483:3483/udp \
      lmscommunity/logitechmediaserver
