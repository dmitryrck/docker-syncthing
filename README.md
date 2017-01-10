This is a Work in Progress.

Example:

    docker run \
      --name=syncthing \
      --hostname="$(hostname)sync" \
      --detach=true \
      --restart=always \
      -p 8384:8384 -p 22000:22000 -p 21027:21027/udp \
      -v /home/syncthing:/root \
      dmitryrck/syncthing syncthing
