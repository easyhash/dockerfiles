FROM ubuntu:bionic

LABEL maintainer="Daniel Bjørnådal <daniel@bjornadal.com>"

# Get needed packages
RUN apt-get -qq update \
  && apt-get -qq install unzip curl

# Create app and data directory
RUN mkdir -p /daemon/data

# Install Daemon
WORKDIR /daemon/
RUN curl -L -o daemon.zip https://github.com/ipbc-dev/bittube/releases/download/2.0.0.4/bittube-linux-x64-v2.0.0.4.zip \
  && unzip daemon.zip -d /daemon \
  && chown -R daemon /daemon \
  && chmod +x /daemon/* \
  && rm -f daemon.zip

USER daemon

EXPOSE 18081 18082
VOLUME [ "/daemon/data" ]
