Console proxy
---

About
----

This tool can help you wrap consoles in tunnel. PS4 consoles is auto-detected via software installed on gateway.
Tunnel for pc and other devices currently not fully supported. All that you must do:
1. Deploy software
2. Add proxies with HTTP and SOCKS5 protocols
3. Connect your consoles
4. Setup other devices such as PC [**manually**](https://www.mathworks.com/help/supportpkg/usrpradio/ug/configure-ethernet-connection-manually-on-windows-10.html)

Requirements
---
- Pc with two network cards
- Fresh installed [**Ubuntu 18.04**](https://releases.ubuntu.com/18.04.5/ubuntu-18.04.5-desktop-amd64.iso)
- Internet connection

HOWTO
----
#### Important. Before any actions read [Basics](docs/basics.md) 

1. Deploy [Admin panel](docs/admin_deployment.md)
2. Deploy [Gateway agent](docs/agent_deployment.md)
3. Add gateway to admin panel [How add gateway to admin?](docs/add_gateway_to_admin.md)
4. [Add proxies](docs/add_proxies_to_admin_panel.md)
5. Connect console to gateway network and admin panel assign vpn to your device
6. Setup internet connection on other devices [**manually**](https://www.mathworks.com/help/supportpkg/usrpradio/ug/configure-ethernet-connection-manually-on-windows-10.html)


Optional
----
To connect caching server to your network you must do some steps in this guide
[Setting up cache server](docs/setup_cache_server.md)