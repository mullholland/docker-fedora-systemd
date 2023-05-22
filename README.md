Docker Fedora Systemd
=====================

This Dockerfile can build containers capable to use systemd.

[![fedora build status](https://img.shields.io/docker/cloud/build/mullholland/fedora.svg)](https://hub.docker.com/repository/docker/mullholland/fedora)

Branches
--------

This repository has multiple tags that relate to Fedora versions.

Fedora Version|Docker image tag|
|--------------|----------------|
|36            |36              |
|latest (37)   |37, latest      |
|rawhide (38)  |38, rawhide     |

Manually starting
-----------------

```shell
docker run \
  --tty \
  --privileged \
  --volume /sys/fs/cgroup:/sys/fs/cgroup:ro \
  mullholland/fedora
```
