Docker Fedora Systemd
=====================

This Dockerfile can build containers capable to use systemd.

Branches
--------

This repository has multiple tags that relate to Fedora versions.

Fedora Version|Docker image tag|
|--------------|----------------|
| 38           | 38             |
| latest (39)  | 39, latest     |
| rawhide (40) | 40, rawhide    |

Manually starting
-----------------

```shell
docker run \
  --tty \
  --privileged \
  --volume /sys/fs/cgroup:/sys/fs/cgroup:ro \
  mullholland/docker-fedora-systemd
```
