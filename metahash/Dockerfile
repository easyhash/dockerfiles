FROM ubuntu:bionic
RUN apt update \
    && apt install -y nano curl 

RUN curl -L -o metahash-proxy.deb https://github.com/metahashorg/node_proxy/releases/download/Proxy_v1.4/metahash-proxy_1.4.deb \
    && dpkg -i metahash-proxy.deb \
    && rm -f metahash-proxy.deb

# Remember to map your HEX-private key to /opt/proxy/proxy_key via VOLUME or SECRET
WORKDIR /opt/proxy

CMD ["./proxy.sh", "start"]