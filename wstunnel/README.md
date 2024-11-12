# Home Assistant Add-on: WSTunnel Server

Access your home assistant SSH server behind a cloudflare tunnel.

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]
![Supports armhf Architecture][armhf-shield]
![Supports armv7 Architecture][armv7-shield]
![Supports i386 Architecture][i386-shield]

[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg

### Instructions

After installing and starting this addon:

1. Install and start **Advanced SSH & Web Terminal** addon
2. Install and configure **Cloudflared** addon with your Cloudflare Tunnel Token
3. Configure tunnel in Cloudflare pointing your (sub)domain to your homeassistant local IP and the port 18809

In your client computer:

1. Install [wstunnel](https://github.com/erebe/wstunnel)
2. `ssh -o ProxyCommand="wstunnel client -L stdio://%h:%p wss://yourdomain.com" hassio@homeassistant`


### Client instructions 

Example for the Raspberry Pi:

```bash
mkdir wstunnel && cd wstunnel
wget https://github.com/erebe/wstunnel/releases/download/v10.1.6/wstunnel_10.1.6_linux_arm64.tar.gz
tar -xvzf *.tar.gz
sudo mv wstunnel /usr/local/bin
sudo chmod +x /usr/local/bin/wstunnel
```

> This is just an example, please check [releases](https://github.com/erebe/wstunnel/releases) for a more recent download link.

Example for macOS:

```bash
brew install wstunnel
```