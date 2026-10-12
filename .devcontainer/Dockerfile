FROM debian:bookworm-slim

ENV XRAY_VERSION=v26.3.27

COPY setup.sh /tmp/setup.sh
COPY config.json /etc/xray/config.json
COPY config.json /etc/xray/g2ray.json

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       bash curl wget unzip ca-certificates libcap2-bin procps openssh-server \
    && rm -rf /var/lib/apt/lists/* \
    && chmod +x /tmp/setup.sh \
    && /tmp/setup.sh \
    && rm /tmp/setup.sh \
    && setcap 'cap_net_bind_service=+ep' /usr/local/bin/xray

EXPOSE 443 8080

CMD ["/usr/local/bin/xray", "run", "-c", "/etc/xray/config.json"]
