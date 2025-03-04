# Docker Stacks
## *arr stack
All data is linked to /data, where a data share is mounted.

All configs are linked to /docker, where another share is mounted specifically for Docker configurations.

When running in Proxmox CTs, put this in config file first:
```
lxc.cgroup2.devices.allow: c 10:200 rwm
lxc.mount.entry: /dev/net dev/net none bind,create=dir
lxc.mount.entry: /dev/net/tun dev/net/tun none bind,create=file
```
Test VPN connections:
```
docker exec -it container_name bash
wget -qO- https://ipinfo.io
```
## Wireguard & Minecraft Stack
All configs are linked to /opt/docker/.

Fix permissions first:
```
sudo chown :docker /opt
sudo chmod 770 /opt
```
## Homarr
wip
## Nginx Proxy Manager
I have my domain pointed to the local IP of the NPM instance, this then acts like a reverse proxy with SSL certs. This way I have subdomains per service I use, all with valid certs.

Compose file is wip.
