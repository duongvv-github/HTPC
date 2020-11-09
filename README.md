# Vincent_Flix
Setting up a home theater pc/server

Current Design:

Client-side:
- Retroarch to play old video games
- Spotify to listen to music
- Kodi to consume media

The client side intended to be installed on a desktop linux environment that is connected to a monitor of some kind.

The server side is not actually a server. Currently all designed to run on one machine and not be exposed to the wilder world.

Setting up 
Server-side Background:
- Watchtower to continually update docker images
- Pihole to block adds
- Organizr as a front end to organize all the apps

Future server-side
- Sonarr to find TV shows on the internet
- Radarr to find movies on the internet
- Transmission + VPN to actually grab it
- Jackett to index torrent sides and pass requests from Sonarr/Radarr to Tranmission


Long term Work
- Automate more configurations via docker to make it reproducable/avoid having to set anything in the app itself
- Actually setup a separate media server to handle data to multiple clients

Actual Server apps
- Jellyfin to actually transcode + serve it
- Ombi for multiple people to make requests Sonarr/Radarr
- MariaDB to keep track of all the data. Need to figure out how Jellyfin/Kodi will sync
- Exposure to outside world, harden everything via Traefik
