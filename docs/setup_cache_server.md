Cache server setup
----
In different network configuration all actions will be same.
1. Set network connection on pc and install caching software
3. Set dns records on gateway for specific domains to this server

----
For setup caching server you need setup internet on pc where cache server will be installed 
[manually](https://help.ubuntu.com/stable/ubuntu-help/net-manual.html.en) with settings from your previously installed **gateway**.
Settings will be such as:
```
Address: 10.1.0.2-10.1.0.9
CIDR: 10.1.0.0/24
Netmask: 255.1.255.0
Gateway: 10.1.0.1
DNS: 1.1.1.1
```
When you checked internet connection on cache pc use info from this [repository](https://github.com/play-just-for-fun/caching-server/) to setup docker and lancache

**To add caching to your infrastructure you need change DNS server settings on your gateway**

Run this shell script with root privileges on **gateway** pc
```shell
#for example
#export CACHE_SERVER_IP=10.1.0.3
export CACHE_SERVER_IP=NEED_TO_CHANGE_THIS

cat <<EOF >/etc/unbound/upstreams-available/sony.conf
server:
  local-zone: "gs2.ww.prod.dl.playstation.net" redirect
  local-data: "gs2.ww.prod.dl.playstation.net 30 IN A $CACHE_SERVER_IP"
EOF

ln -s /etc/unbound/upstreams-available/sony.conf /etc/unbound/upstreams-enabled/sony.conf
systemctl restart unbound

```
Reconnect your device to internet for apply new settings
