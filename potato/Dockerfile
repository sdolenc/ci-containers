FROM penz/debian-potato-i386

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y git tar gzip && echo echo
RUN echo "deb http://archive.debian.org/debian woody main" >> /etc/apt/sources.list
RUN apt-get update && apt-get install -y ssh ca-certificates && echo echo

# cleanup
RUN rm -rf /var/lib/apt/lists/*
