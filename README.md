# DockerMiner
Mine cryptocurrencies with Nvidia Docker and get paid in Bitcoin </br>
[![Docker Automated build](https://img.shields.io/docker/automated/jrottenberg/ffmpeg.svg)](https://hub.docker.com/r/yvictor/dockerminer/builds/)

## Environment Requirements
- [Docker CE](https://www.docker.com/community-edition#/download) </br>
`curl -sL https://get.docker.com | sh`
- [NVIDIA GPU with Architecture > Fermi (2.1)](https://github.com/NVIDIA/nvidia-docker/wiki/Frequently-Asked-Questions#how-do-i-install-the-nvidia-driver)
- [NVIDIA drivers ~= 361.93](http://www.nvidia.com/object/unix.html)
- [nvidia-docker](https://github.com/NVIDIA/nvidia-docker)
    - Xenial x86_64 </br>
    `sudo apt-get install -y nvidia-docker2 && sudo pkill -SIGHUP dockerd`
    - CentOS/RHEL 7 x86_64 </br>
    `sudo yum install -y nvidia-docker2 && sudo pkill -SIGHUP dockerd`

## Start nvidia docker miner
``` sh
nvidia-docker run --name miner \
-e l=equihash.usa.nicehash.com:3335 \
-e cd=0 \
-e addr=376DDkR38hSBHZXLJdvAXTTzDsuyUpVU4S.miner1 \
-e t=1 \
-d yvictor/dockerminer
```
- [command guide](https://github.com/nicehash/nheqminer#run-instructions)
- change addr=<your_bitcoin_wallet_address>

## Build your own nvidia docker image
```
git clone https://github.com/Yvictor/DockerMiner.git
cd DockerMiner
docker build -t {image_name} .
```
