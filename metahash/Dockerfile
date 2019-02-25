FROM ubuntu:bionic
RUN apt update \
    && apt install -y nano curl libssl1.0.0

RUN curl -L -o metahash-proxy.deb https://github.com/metahashorg/node_proxy/releases/download/Proxy_v1.4/metahash-proxy_1.4.deb \
    && dpkg -i metahash-proxy.deb \
    && rm -f metahash-proxy.deb


WORKDIR /opt/proxy
RUN mkdir key

# Remember to map your HEX-private key to /opt/proxy/proxy_key via VOLUME or SECRET
CMD ./proxy key/proxy_key proxy_config 9999 1000000