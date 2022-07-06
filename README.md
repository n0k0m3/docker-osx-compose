# Guide to install docker-OSX
- First run install macOS with appriopriate tag (default: `monterey`)
```sh
export TAG=<set_tag_here>
docker compose -f docker-compose.first-run.yml up
```
- Find `mac_hdd_ng.img` contains installation of macOS and copy to working folder
```sh
sudo find /var/lib/docker -size +10G | grep mac_hdd_ng.img
sudo cp <mac_hdd_ng_img_PATH> .
```
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
- Run `docker-compose.yml` to start the docker-OSX
```sh
docker compose up
```