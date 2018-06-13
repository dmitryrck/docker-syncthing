# Syncthing using docker

Example:

```terminal
$ docker run \
  --name=syncthing \
  --hostname="$(hostname)sync" \
  --detach=true \
  -p 8384:8384 -p 22000:22000 -p 21027:21027/udp \
  -v /home/syncthing:/root \
  dmitryrck/syncthing syncthing
```

You might want to use `--restart=always` too.

This is how I use it:

```terminal
#!/bin/bash

set -xe

docker run --rm \
  --detach=true \
  --name=syncthing \
  --hostname="$(hostname)sync" \
  -p 8384:8384 -p 22001:22000 -p 21028:21027/udp \
  -u $(id -u) \
  -e HOME=/home/sync \
  -v $HOME/Sync:/home/sync \
  dmitryrck/syncthing syncthing
```
