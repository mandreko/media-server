# media-server

Docker configuration to create Usenet and Torrent downloading system using Sonarr, Radarr, Deluge (over PIA OpenVPN), NZBGet, and Plex

## First run

- install [Docker](https://www.docker.com/)
- create a [Plex accout](https://www.plex.tv/)
- clone this repository
- Configure OpenVPN-Client with username/password and any other specific settings (See below section)
- get your Plex claim token at https://www.plex.tv/claim/ and put it in the ".env" file
- configure other settings in ".env" file to match your setup
- run docker-compose up -d`
- enjoy

## Config

### OpenVPN-Client

Open-VPN Client is used to force Deluge over a VPN to avoid automated copyright notices from your ISP.

- If using [PIA](http://www.privateinternetaccess.com), add your username and password to ~/openvpn-client/vpn.auth. For other VPN providers, you'll want to read about how to configure them with OpenVPN clients.

### NZBGet

NZBGet downloads content using Usenet

- Add a usenet server, along with credentials from the Settings.

### Deluge

Deluge downloads content using BitTorrent

- none

### Plex

Plex is used to play multimedia files.

- authenticate with your Plex credentials
- configure TV and Movies paths to /data/TV and /data/Movies

### Sonarr

Sonarr is used to track and manage TV shows. It utilizes downloaders to actually download them.

- configure authentication
- add Indexers for NZBs, based on what you have
- add Plex Media Server to "Connect" tab, using your Plex credentials

### Radarr

Similar to Sonarr (actually forked code) Radarr is used to track and manage Movies.

- configure authentication
- add Indexers for NZBs, based on what you have
- add Plex Media Server to "Connect" tab, using your Plex credentials
