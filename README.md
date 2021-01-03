# Vincent_Flix
Setting up a home theater pc/server ontop of a rasberry pi 4/ubuntu OS

Current Design (1.1):

Client-side:
- ~~Retroarch to play old video games~~ Will use retropi installed directly on ubuntu
- Spotify to listen to music directly on ubuntu (will need to debug app)
- firefox and general web browser stuff
- Transmission to torrent stuff (vpn later)

The client side intended to be installed on a desktop linux environment that is connected to a monitor of some kind.

The server side is not actually a server. Currently all designed to run on one machine and not be exposed to the wilder world.

Setting up 
Server-side Background:
- Watchtower to continually update docker images
- Pihole to block adds in docker

Future server-side
- Kodi to organize and consume media
- Organizr as a front end to organize all the apps
- Sonarr to find TV shows on the internet
- Radarr to find movies on the internet
- VPN to find torrent
- Jackett to index torrent sides and pass requests from Sonarr/Radarr to Transmission


Long term Work
- Automate more configurations via docker to make it reproducable/avoid having to set anything in the app itself. In particular, save retropi controller setup and kodi config 
- ~~Actually setup a separate media server to handle data to multiple clients~~ Not going to serve other people/remote users

Actual Server apps
- ~~Jellyfin to actually transcode + serve it~~
- Ombi for multiple people to make requests Sonarr/Radarr
- MariaDB to keep track of all the data. Need to figure out how Jellyfin/Kodi will sync
- Exposure to outside world, harden everything via Traefik
