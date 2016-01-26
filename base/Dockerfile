FROM debian:jessie
MAINTAINER Neven Vucinic [neven.vucinic@gmail.com]

## Set noninteractive deb env

ENV DEBIAN_FRONTEND noninteractive

## Fix time zone
RUN echo "Europe/Zagreb" > /etc/timezone
RUN dpkg-reconfigure -f noninteractive tzdata

## Update Debian and install locales

RUN apt-get update \
&&  apt-get upgrade -y \
&& apt-get install locales -yq 

# Set default locale for the environment
ENV LC_ALL C.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
