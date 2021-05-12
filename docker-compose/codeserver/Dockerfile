FROM ghcr.io/linuxserver/code-server

ENV DEBIAN_FRONTEND=noninteractive

RUN true \
# Any command which returns non-zero exit code will cause this shell script to exit immediately:
    && set -e \
# Activate debugging to show execution details: all commands will be printed before execution
    && set -x \
# OS Aktualisieren
    && apt-get update \
    && apt-get dist-upgrade -y \
# Pakete fuer Java Entwicklung und Chrome install.
    && apt-get install openjdk-11-jdk-headless maven -y \
# Putzen
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Chrome Installation
ADD https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb /tmp/

RUN true \
    && apt-get update \
    && apt-get install gdebi-core -y \ 
    && gdebi --non-interactive /tmp/google-chrome-stable_current_amd64.deb \
# Putzen
    && rm /tmp/google-chrome-stable_current_amd64.deb \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
