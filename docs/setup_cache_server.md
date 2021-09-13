Cache server setup
----
For setup caching server you need setup internet on pc where cache server will be installed 
[manually](https://help.ubuntu.com/stable/ubuntu-help/net-manual.html.en) with settings from your previously installed gateway . After this use info from this [repository](https://github.com/play-just-for-fun/caching-server/)

**To add caching to your infrastructure you need change DNS server settings on your gateway in your DHCP Configuration with following commands**
```shell
sudo sed -i 's/domain-name-servers.*/domain-name-servers IP_OF_YOUR_DNS_SERVER;/' /etc/dhcp/dhcpd.conf
sudo systemctl restart isc-dhcp-server
```
Reconnect your device to apply new settings