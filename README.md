# Setup

1. Get a webhost and install docker on it. Follow offical instructions.
2. Fork this repo.
3. Configure your bit torrent sync setup (btsync.conf) - essentially all your want to change here is the shared folder secrets (check the docs on how to generate them). Keep the rest of the settings the same. My example includes both a backups and a torrents folder. Make sure you set a username / password for transmissions web interface as well.
4. Deploy all the code to the server (git clone)
5. docker-compose build && docker-compose up
6. Make sure ports 80, 45555 and 3369 are open
7. Install btsync on your local machines and use the folder secrets you made earlier.
 
You can get torrents up to the machine one of two ways. Either go to the web interface (port 80) and upload to the transmission daemon or just cope the files into the btsync folder torrents/watch where they will be automatically picked up by transmission.
