# Docker Compose for Docker-OSX
This is the guide to install docker-OSX with minimal setup.
## Requirements
- Docker CLI
- Docker Compose

## How-to
**First run:**
- Install macOS docker with appriopriate tag, refer to [docker-osx Dockerhub](https://hub.docker.com/r/sickcodes/docker-osx/tags) (default: `monterey`)
```sh
export TAG=<set_tag_here>
docker compose -f docker-compose.first-run.yml up
```
- Find `mac_hdd_ng.img` contains installation of macOS and copy to working folder
```sh
sudo find /var/lib/docker -size +10G | grep mac_hdd_ng.img
sudo cp <mac_hdd_ng_img_PATH> .
```

**Configuration:**
- (Optional) Create/edit `.env` file with following variables for iMessage and rescale resolution:
```
GENERATE_SPECIFIC=true
DEVICE_MODEL=<DEVICE_MODEL>
SERIAL=<SERIAL>
BOARD_SERIAL=<BOARD_SERIAL>
UUID=<UUID>
MAC_ADDRESS=<MAC_ADDRESS>
WIDTH="1280"
HEIGHT="720"
```

**Subsequent runs:**
- Run `docker-compose.yml` to start the docker-OSX
```sh
docker compose up
```