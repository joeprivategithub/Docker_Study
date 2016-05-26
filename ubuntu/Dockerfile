#
# MAINTAINER        Michael Joe <michael_joe@126.com>
# DOCKER-VERSION    1.0.0
#
# Dockerizing Ubuntu 14.01: Dockerfile for building ubuntu base images
#
FROM	ubuntu:latest
MAINTAINER	Michael Joe  <michael_joe@126.com>

ENV	TZ "Asia/Shanghai"

WORKDIR /root/
RUN	apt-get update
RUN	apt-get -y install vim htop git git-core bzip2 curl tar wget ssh
RUN	apt-get -y install gcc  make automake  python  ntpdate dos2unix 
RUN	apt-get autoclean
RUN	passwd -l news 
RUN	passwd -l games
RUN	sed -i '/ForwardAgent/cForwardAgent yes'  /etc/ssh/ssh_config
RUN	rm /bin/sh
RUN	ln -s /bin/bash  /bin/sh
RUN	echo  "highlight Comment ctermfg=blue guifg=blue" > /root/.vimrc
RUN	mkdir /root/.ssh
ADD	authorized_keys /root/.ssh/

EXPOSE	22
EXPOSE	80
EXPOSE	8080
VOLUME	["/data"]

ONBUILD RUN apt-get update
