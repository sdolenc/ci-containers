FROM debian:stable-slim

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak; \
    grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list; \
    \
    apt-get update; \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes --no-install-recommends ca-certificates; \
    \
    apt-get -y autoremove; \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/*
