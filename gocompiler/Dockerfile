FROM ubuntu:latest

ENV DEBIAN_FRONTEND noninteractive

RUN apt update && \
	apt install -y --no-install-recommends \
		golang \
		git-core \
		build-essential \
		netbase \
		&& \
	rm -rf /var/lib/apt/lists/*

