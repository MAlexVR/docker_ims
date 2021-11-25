# docker_ims
Docker files to build and run kamailio IMS in a docker

## Tested Setup

Docker host machine

- Ubuntu 18.04 and 20.04

## Build and Execution Instructions

* Mandatory requirements:
	* [docker-ce](https://docs.docker.com/install/linux/docker-ce/ubuntu)
	* [docker-compose](https://docs.docker.com/compose)

* Optional
	* [Homer SIP Capture Node](https://github.com/sipcapture/homer/wiki/Quick-Install#-docker-install)

Clone repository and build base docker image of open5gs, kamailio, ueransim

```
git clone https://github.com/MauricioV/docker_ims
cd docker_ims/ims_base
docker build --no-cache --force-rm -t docker_kamailio .
```

### Build and Run using docker-compose

```
cd ..
set -a
source .env
docker-compose build --no-cache
docker-compose up
```

## Register a UE information in the FoHSS

Open (http://<DOCKER_HOST_IP>:8080) in a web browser, where <DOCKER_HOST_IP> is the IP of the machine/VM running the IMS containers. Login with following credentials
```
Username : hssAdmin
Password : hss
```


