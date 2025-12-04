# Homelab Docker Compose scripts

## Index

1. Reverse Proxy
    1. [Caddy](./caddy/README.md)

2. Domain Name Servers
    1. [AdGuard](./adguard/README.md)

## Managing Docker Volumes

I manage to my docker volumes my mounting a directory from my host machine to the container.

```bash
# set a directory path (Change it to any other path)
$ export DOCKER_VOLUMES=${HOME}/docker-volumes

# create directory
$ mkdir -p ${DOCKER_VOLUMES}

# change permissions
chmod 755 ${DOCKER_VOLUMES}
```
