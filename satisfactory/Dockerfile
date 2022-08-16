FROM ubuntu:latest

ENV DEBIAN_FRONTEND noninteractive

RUN apt update && \
	apt install -y --no-install-recommends \
		software-properties-common \
		apt-transport-https \
		&& \
	rm -rf /var/lib/apt/lists/*

RUN echo steam steam/question select "I AGREE" | debconf-set-selections
RUN echo steam steam/license note '' | debconf-set-selections

RUN add-apt-repository multiverse && \
	dpkg --add-architecture i386 && \
	apt update && \
	apt install -y --no-install-recommends \
		lib32gcc1 \
		steamcmd \
		&& \
	rm -rf /var/lib/apt/lists/*

RUN useradd -ms /bin/bash satisfactory
USER satisfactory
WORKDIR /home/satisfactory

RUN /usr/games/steamcmd \ 
	+force_install_dir ~/SatisfactoryDedicatedServer \
	+login anonymous \
	+app_update 1690800  \
	-beta public \
	validate \
	+quit

EXPOSE 7777/udp 15000/udp 15777/udp



