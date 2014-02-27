#
# perl env
#
# https://github.com/battlemidget/docker-recipes/

FROM ubuntu:latest
MAINTAINER Adam Stokes <adam.stokes@ubuntu.com>

# locales
ENV DEBIAN_FRONTEND noninteractive
RUN locale-gen en_US.UTF-8 && dpkg-reconfigure locales

RUN echo "deb http://archive.ubuntu.com/ubuntu trusty main universe multiverse" > /etc/apt/sources.list
RUN echo "deb http://archive.ubuntu.com/ubuntu trusty-updates main universe multiverse" >> /etc/apt/sources.list
RUN echo "deb http://archive.ubuntu.com/ubuntu trusty-proposed main universe multiverse" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y

# Install basic packages.
RUN apt-get install -y curl git perl cpanminus cpanoutdated

# Set working directory.
ENV HOME /root
WORKDIR /root

RUN cpanm --notest https://github.com/battlemidget/Task-ADAMJS.git
RUN task-adamjs-install
