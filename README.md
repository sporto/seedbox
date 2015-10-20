# Setup

## Setup server

- Install git e.g. apt-get install -y git

- Install docker and docker-compose, see:

https://docs.docker.com/installation/
https://docs.docker.com/compose/install/

- Clone this repo in your server e.g. git clone https://github.com/.../seedbox-setup.git

- Edit `docker-compose.yml`, setup transmission web interface username and password

- Generate 2 secrets for bittorrent sync:

```
docker-compose run btsync bin/bash
./btsync --generate-secret
./btsync --generate-secret
# Copy the generated secrets
exit
```

Edit data/btsync.conf and paste the generated secrets


- Run docker compose:

```
docker-compose up
```

- Make sure ports 80, 45555 and 3369 are open

```
nc -z my.server.ip 80
nc -z my.server.ip 45555
nc -z my.server.ip 3369
```

## Setup local

- Install btsync on your local machines and use the folder secrets you made earlier.

# Usage

You can get torrents up to the machine one of two ways. Either go to the web interface (port 80) and upload to the transmission daemon or just cope the files into the btsync folder torrents/watch where they will be automatically picked up by transmission.
