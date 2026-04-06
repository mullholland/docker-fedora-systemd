FROM fedora:43

LABEL maintainer="mullholland"
LABEL build_date="2026-04-05"

ENV container=docker

# Enable systemd.
RUN dnf --nogpgcheck -y install systemd && dnf clean all && \
  (cd /lib/systemd/system/sysinit.target.wants/ ; for i in * ; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i ; done) ; \
  rm -f /lib/systemd/system/multi-user.target.wants/* ;\
  rm -f /etc/systemd/system/*.wants/* ;\
  rm -f /lib/systemd/system/local-fs.target.wants/* ; \
  rm -f /lib/systemd/system/sockets.target.wants/*udev* ; \
  rm -f /lib/systemd/system/sockets.target.wants/*initctl* ; \
  rm -f /lib/systemd/system/basic.target.wants/* ;\
  rm -f /lib/systemd/system/anaconda.target.wants/*

# Install requirements.
RUN dnf makecache \
 && dnf upgrade -y \
 && dnf --nogpgcheck -y install \
      sudo \
      which \
      ca-certificates \
      iproute \
      util-linux \
      python3 \
      python3-pip \
  && dnf clean all

# Disable requiretty.
RUN sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers

VOLUME ["/sys/fs/cgroup"]
CMD ["/sbin/init"]
