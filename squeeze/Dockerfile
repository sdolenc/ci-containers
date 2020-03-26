FROM debian/eol:squeeze

# remove security to help speed up apt-get (and reduce failures)
RUN echo "deb http://archive.debian.org/debian-backports squeeze-backports main" >> /etc/apt/sources.list
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN apt-get update && echo success1
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes tar gzip ca-certificates && echo sucess2
# git
RUN apt-get install -y --force-yes -t squeeze-backports git && echo success3
# lsblk
RUN echo "deb http://archive.debian.org/debian wheezy main" >> /etc/apt/sources.list
RUN apt-get update && echo success4
RUN apt-get install -y --force-yes util-linux && lsblk && echo success5

# cleanup
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list
RUN apt-get update && echo success6
RUN apt-get -y autoremove && echo success7
RUN apt-get -y clean && echo success8
RUN rm -rf /var/lib/apt/lists/*
