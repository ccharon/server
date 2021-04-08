FROM ghcr.io/linuxserver/code-server:latest
RUN true \
# Any command which returns non-zero exit code will cause this shell script to exit immediately:
  && set -e \

# Activate debugging to show execution details: all commands will be printed before execution
  && set -x \

# OS Aktualisieren
  && apt-get update \
  && apt-get dist-upgrade -y \

# Pakete fuer Java Entwicklung
  && apt-get install openjdk-11-jdk-headless maven -y \

# Chrome Installation
  && apt-get install gdebi-core wget -y \
  && wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb \
  && gdebi --non-interactive google-chrome-stable_current_amd64.deb \
  && rm google-chrome-stable_current_amd64.deb \

# Putzen
  && apt-get clean
