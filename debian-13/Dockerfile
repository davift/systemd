FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive \
    container=docker \
    LANG=en_US.UTF-8 \
    LANGUAGE=en_US:en

RUN apt update && apt install -y \
    systemd \
    systemd-sysv \
    apt-transport-https \
    ca-certificates \
    lsb-release && \
    apt clean -y && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN cd /lib/systemd/system/sysinit.target.wants/ ; \
    ls | grep -v systemd-tmpfiles-setup | xargs rm -f $1 ; \
    rm -f /lib/systemd/system/multi-user.target.wants/* ;\
    rm -f /etc/systemd/system/*.wants/* ;\
    rm -f /lib/systemd/system/local-fs.target.wants/* ; \
    rm -f /lib/systemd/system/sockets.target.wants/*udev* ; \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl* ; \
    rm -f /lib/systemd/system/basic.target.wants/* ;\
    rm -f /lib/systemd/system/anaconda.target.wants/* ; \
    rm -f /lib/systemd/system/plymouth* ; \
    rm -f /lib/systemd/system/systemd-update-utmp* ; \
    systemctl mask openipmi.service

CMD ["/lib/systemd/systemd"]

