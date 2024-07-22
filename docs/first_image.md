# Build your first image

## Install dependencies

Currently, due to our dependency on [`debos`](https://github.com/go-debos/debos/issues/363), we can only run `rbuild` on x86 based system. If you are building in a virtual machine, you need to [enable nested virtualization](https://github.com/Anaple/rbuild/issues/16#issuecomment-1534176754), as KVM is required for building the image.

### Debian 12 / Ubuntu 22.04

```bash
sudo apt update
sudo apt install -y git

# Podman (recommended)
sudo apt install -y podman podman-docker
sudo touch /etc/containers/nodocker
# Docker
#sudo apt install -y docker.io
#sudo adduser $USER docker
#sudo reboot
```

## Check out the code

```bash
git clone https://github.com/Anaple/rbuild.git
```

## Build your first image

Once the repo is cloned on your machine, you can run `rbuild` without any arguments to check the help message:

```bash
cd rbuild
./rbuild
```

Most options listed in the help messages are targetting at developers. If you only want to build an image locally, you can run `rbuild` with only the required arguments:

```bash
# Build radxa-cm3-sodimm-io image with default OS (currently Debian Bullseye) and flavor (CLI)
./rbuild radxa-cm3-sodimm-io
# Build rock-5b Debian image with KDE
./rbuild rock-5b kde
```

Supported products, suites, and flavors are listed at the end of the help message.

```admonish
Radxa supports and recommends Debian on all Radxa products.

Building Ubuntu requires [special instruction](dev/ubuntu.md).
```
