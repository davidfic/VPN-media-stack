# Docker Compose stack for my media station

## Torrent system

Radarr and Sonarr do the work of finding the media you want and they will pass it off to qbittorrent to handle the downloading. 

This setup is using PIA VPN to connect to a different region to avoid showing torrent traffic to my ISP.

Downlods are saved to their respective locaiton for either movies or tv. 


## Traefix 

Reverse proxy to tie it all together and allow for easy access via simple DNS names. 
Also allows access to the containers using the vpn network 

## VPN Info

I went with PIA for this. You can substitue other VPN system fairly easily. 
Copy the auth.conf.example file to auth.conf and replace the values with your actual PIA credentials


## Additional Info

Things that you will need to update to use this.

* update the paths to reflect where you are storing your confings and media
* supply an auth.conf file with your pia credentials. 

## Misc containers

### Jackett

Helps simplify accessing different torernt systems by providing a nice abstration for radarr and sonarr

### Watchtower

Monitors the docker.sock and will constantly check for updated versions of all the running containers and pulls them when it finds it and restarts the container. Nice easy way to keep things from getting stale

### Bazarr

Will go out and find subtitles for movies and tv shows that need it

### Tautulli

A way to visualize who is watching, what they are watching and a good overall view of the usage of your Plex system


