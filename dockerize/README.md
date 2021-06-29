# Docker Installation

## Prerequisites

- Raspberry Pi 4 with a running Raspberry Pi OS
- SSH connection enabled

## Installation steps

Make sure the raspberry pi is running latest software.

```sh
sudo apt update
sudo apt upgrade
```

Docker provides a handy script to install the docker.

```sh
curl -sSL https://get.docker.com | sh
```

And we can check the docker service is running.

```sh
systemctl status docker
```

By default, only root user has a privilege to run the container. We need to add non-root user to the docker group which enable us to execute docker commands.

```sh
sudo usermod -aG docker ${USER}
```

And check whether you are already in the docker group.

```sh
groups ${USER}
```

By default, Raspberry Pi OS has python3 installed. We need to install pip3 and other dependencies before installing docker-compose.

```sh
sudo apt install -y phython3-pip libffi-dev
```

Once the python3 and pip3 installed, we can install docker-compose.

```sh
sudo pip3 install docker-compose
```
