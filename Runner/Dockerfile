# ----------------------------------
# CursedMod Runner DockerFile
# Environment: SteamCmd
# Minimum Panel Version: 0.6.0
# ----------------------------------
FROM steamcmd/steamcmd:ubuntu-22

MAINTAINER Jesus-QC, <support@jesusqc.es>

RUN echo Hello

USER container
ENV  USER=container HOME=/home/container

WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]
