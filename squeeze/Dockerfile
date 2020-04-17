FROM debian/eol:squeeze

RUN echo "deb http://archive.debian.org/debian-backports squeeze-backports main" >> /etc/apt/sources.list; \
    cp /etc/apt/sources.list /etc/apt/sources.list.bak; \
    grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list; \
    \
    apt-get update; \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes --no-install-recommends ca-certificates; \
    \
    echo "deb http://archive.debian.org/debian wheezy main" >> /etc/apt/sources.list; \
    apt-get update; \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes --no-install-recommends util-linux && lsblk; \
    \
    grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list; \
    apt-get update; \
    apt-get -y autoremove; \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/*
