Agent deployment
-----

Requirements
---
- RAM: min 4Gb
- HDD: min 80Gb
- OS: Ubuntu 18.04 LTS
- Network: two 1Gb network cards  

_Note_: _For small deployments you can install agent on same pc that admin panel installed._
_In this case on installing step set admin panel address 127.0.0.1_

1.Go to directory where you download vpntools.tar.gz archive 
```shell
sudo mkdir -p /tmp/vpnadmin && sudo tar -xf vpntools.tar.gz -C /tmp/vpnadmin
sudo cp -rp /tmp/vpnadmin/vpnagent /tmp/vpnagent
```
2. Run install script
```shell
sudo bash /tmp/vpnadmin/devops/deploy_agent.sh
```
3. Answer the questions asked by installation script.
4. When all steps will be finished you will see such as this. **Store this info**. You will need it later 
```shell
---------------------------------------------------------------------------
Add this gateway to admin panel
Go to http://192.168.10.10:9000
Admin panel->Gws->Add gw
Name gw1
Ip 192.168.10.25
Only pc in 10.1.0.0/29 subnetwork has direct access to internet without proxy. This ips can be set manually with settings:
Address: 10.1.0.2-10.1.0.9
CIDR: 10.1.0.0/24
Netmask: 255.255.255.0
Gateway: 10.1.0.1
DNS: 10.1.0.1  
---------------------------------------------------------------------------
```
5. For internet access from pc connected to gateway you need manually setup network connection
---

Additional info
---
To have direct internet connection on your devices you need to setup manual ip on your device in /29 cidr. 
