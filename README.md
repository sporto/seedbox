# Setup

## Setup server

Install git e.g. apt-get install -y git

Install docker and docker-compose, see:

- https://docs.docker.com/installation/
- https://docs.docker.com/compose/install/

Clone this repo in your server e.g. git clone https://github.com/.../seedbox-setup.git

### Transmission credentials

Edit transmission.env

### Sync config

- Generate a secret for bittorrent sync:

```
docker-compose run btsync bin/bash
./btsync --generate-secret
# Copy the generated secret
exit
```

Edit `data/sync.conf` and paste the generated secret


- Run docker compose:

```
docker-compose up
```

- Make sure ports 80, 51413 and 3369 are open

```
nc -z my.server.ip 80
nc -z my.server.ip 51413
nc -z my.server.ip 55555
```

## Setup local

- Install [btsync](https://www.getsync.com/) on your local machines and use `Manual connection` using the folder secrets you made earlier.

# Usage

You can get torrents up to the machine one of two ways. Either:

- Go to the web interface (port 80) and upload to the transmission daemon or 
- just copy the files into the btsync folder `torrents/watch` where they will be automatically picked up by transmission.
