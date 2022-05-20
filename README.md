# docker-vrising<br>
Minimal Ubuntu 22.04 container with wine, mono and dotnet packages<br>
Goal is to run a dedicated game server.<br>
In this case: a V-Rising dedicated server<br>
Refer to https://github.com/StunlockStudios/vrising-dedicated-server-instructions for json configuration settings.

![Trueosiris Rules](https://img.shields.io/badge/trueosiris-rules-f08060) 
[![Docker Pulls](https://badgen.net/docker/pulls/trueosiris/vrising?icon=docker&label=pulls)](https://hub.docker.com/r/trueosiris/vrising/) 
[![Docker Stars](https://badgen.net/docker/stars/trueosiris/vrising?icon=docker&label=stars)](https://hub.docker.com/r/trueosiris/vrising/) 
[![Docker Image Size](https://badgen.net/docker/size/trueosiris/vrising?icon=docker&label=image%20size)](https://hub.docker.com/r/trueosiris/vrising/) 
![Github stars](https://badgen.net/github/stars/trueosiris/docker-vrising?icon=github&label=stars) 
![Github forks](https://badgen.net/github/forks/trueosiris/docker-vrising?icon=github&label=forks) 
![Github issues](https://img.shields.io/github/issues/TrueOsiris/docker-vrising)
![Github last-commit](https://img.shields.io/github/last-commit/TrueOsiris/docker-vrising)

### setup

### environment variables

| Environment Variable | Key | Description |
| -------------------- | ---------------------------- | ------------------------------------------------------------------------------- |
| TZ | Europe/Brussels | timezone for ntpdate |

### ports

| Exposed Container port | Type |
| ---------------------- | ---- |
| 9876 | UDP |
| 9877 | UDP |

### volumes

| Volume                    | Container path                                                   | Description |
| ------------------------- | ---------------------------------------------------------------- | ----------------------------------------------- |
| steam install path    | /mnt/vrising/server | path to hold the dedicated server files |
| world | /mnt/vrising/persistentdata | path that holds the world files |

### Run command

    docker run -d --name='vrising' \
    --net='bridge' \
    -e TZ="Europe/Paris" \
    -v '/path/on/host/dedicatedserverfiles':'/mnt/vrising/server':'rw' \
    -v '/path/on/host/persistentdata':'/mnt/vrising/persistentdata':'rw' \
    -p 9876:9876 \
    -p 9877:9877 \
    'trueosiris/vrising'

### links

github repo: https://github.com/TrueOsiris/docker-vrising <br>
dockerhub repo: https://hub.docker.com/repository/docker/trueosiris/vrising <br>

