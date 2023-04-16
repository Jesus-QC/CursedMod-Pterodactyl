# ----------------------------------
# CursedMod Runner DockerFile
# Environment: Ubuntu
# Minimum Panel Version: 0.6.0
# ----------------------------------
FROM ubuntu:20.04

MAINTAINER Jesus-QC, <support@jesusqc.es>

USER root

RUN echo steamcmd steam/question select "I AGREE" | debconf-set-selections
RUN echo steamcmd steam/license note '' | debconf-set-selections

ARG DEBIAN_FRONTEND=noninteractive
RUN dpkg --add-architecture i386 \
 && apt-get update -y \
 && apt-get install -y --no-install-recommends ca-certificates locales steamcmd \
 && rm -rf /var/lib/apt/lists/*

RUN locale-gen en_US.UTF-8
ENV LANG 'en_US.UTF-8'
ENV LANGUAGE 'en_US:en'

RUN echo Hello

RUN adduser --disabled-password --home /home/container container
RUN usermod -a -G container container
RUN chown -R container:container /home/container

USER container
ENV  USER=container HOME=/home/container

WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD ["/bin/bash", "/entrypoint.sh"]
