# podman-buildah-skopeo-runc-installation-on-ubuntu

following tools install procudure.

- podman
- buildah
- skopeo
- runc

and easy tutorials.

# Prerquirement
- Ubuntu 18.04LTS

# Notice

There is a problem that Systemd doesn't work on WSL2 Ubuntu 18.04LTS, and podman doesn't work completely.

# Installation

## Podman

```
# apt-get update -qq
# apt-get install -qq -y software-properties-common uidmap
# add-apt-repository -y ppa:projectatomic/ppa
# apt-get -qq -y install podman
# podman version
Version:            1.5.1
RemoteAPI Version:  1
Go Version:         go1.10.4
OS/Arch:            linux/amd64
```

reference 
https://github.com/containers/libpod/blob/master/install.md

## buildah

```
# apt-get -qq -y install buildah
# buildah version
Version:         1.10.1
Go Version:      go1.10.4
Image Spec:      1.0.1
Runtime Spec:    1.0.1-dev
CNI Spec:        0.4.0
libcni Version:
Git Commit:
Built:           Fri Aug  9 05:29:48 2019
OS/Arch:         linux/amd64
```

reference
https://github.com/containers/buildah/blob/master/install.md


## Golang

```
# add-apt-repository ppa:longsleep/golang-backports
# apt-get update
# apt-get install golang-go
# go version
go version go1.13 linux/amd64
# mkdir -p go/bin
# mkdir -p go/src
# mkdir -p go/pkg
# echo 'export GOPATH=$HOME/go' >> .bashrc 
# echo 'export PATH=$PATH:$GOPATH/bin' >> .bashrc
# source .bashrc
```

reference
https://github.com/golang/go/wiki/Ubuntu

## skopeo

```

# apt install libgpgme-dev libassuan-dev libdevmapper-dev libostree-dev
# git clone https://github.com/containers/skopeo $GOPATH/src/github.com/containers/skopeo
# cd $GOPATH/src/github.com/containers/skopeo
# make binary-local
# mv skopeo ~/go/bin/
# skopeo -version
skopeo version 0.1.40-dev commit: 5ae6b16c0f318bf4d14ef0e19e8aa27b6c072670
```

reference
https://github.com/containers/skopeo

## runc

```
# apt-get install libseccomp-dev
# mkdir $GOPATH/src/github.com/opencontainers
# cd $GOPATH/src/github.com/opencontainers
# git clone https://github.com/opencontainers/runc
# cd runc
# make
# make install
install -D -m0755 runc /usr/local/sbin/runc
# runc -version
runc version 1.0.0-rc8+dev
commit: bf27c2f86dac5e7bd33880b33e4b542ad6a0289e
spec: 1.0.1-dev
```

reference
https://github.com/opencontainers/runc

# Reference

## Useful Knowledges

https://computingforgeeks.com/how-to-install-podman-on-ubuntu/

https://developers.redhat.com/articles/podman-next-generation-linux-container-tools/

https://developers.redhat.com/blog/2019/09/13/develop-with-node-js-in-a-container-on-red-hat-enterprise-linux/

## Product Manuals

Buildah

https://access.redhat.com/documentation/ja-jp/red_hat_enterprise_linux/8/html/building_running_and_managing_containers/building-container-images-with-buildah_building-running-and-managing-containers#understanding_buildah

Podman

https://access.redhat.com/documentation/ja-jp/red_hat_enterprise_linux/8/html/building_running_and_managing_containers/using-systemd-with-containers_building-running-and-managing-containers

SKOPEO

https://access.redhat.com/documentation/ja-jp/red_hat_enterprise_linux/8/html/building_running_and_managing_containers/skopeo

RUNC

https://access.redhat.com/documentation/ja-jp/red_hat_enterprise_linux/8/html/building_running_and_managing_containers/runc

