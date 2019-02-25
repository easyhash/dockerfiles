FROM ubuntu:bionic
RUN apt update \
    && apt install -y nano curl 

RUN curl -L -o metahash-proxy.deb https://github.com/metahashorg/node_proxy/releases/download/Proxy_v1.4/metahash-proxy_1.4.deb \
    && dpkg -i metahash-proxy.deb \
    && rm -f metahash-proxy.deb


WORKDIR /opt/proxy
RUN mkdir key

# Change key location to /opt/proxy/key/proxy_key for better VOLUME and SECRET support
# Remember to map your HEX-private key to /opt/proxy/proxy_key via VOLUME or SECRET
RUN sed 's/key=proxy_key/key=key\/proxy_key/g' proxy.sh

CMD ["./proxy.sh", "start"]