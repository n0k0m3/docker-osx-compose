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
- (Optional) Create an `.env` file following the template in `.env.template`
- (Optional) `docker-compose` supports `docker-compose.override.yml` file for additional config. Read [here](https://docs.docker.com/compose/extends/#adding-and-overriding-configuration) on how to add or override configuration in the mail compose file.

**Subsequent runs:**
- Run `docker-compose.yml` to start the docker-OSX
```sh
docker compose up
```
