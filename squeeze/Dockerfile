FROM debian/eol:squeeze

# installs
RUN apt-get update && echo success1
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes ssh tar gzip ca-certificates && echo sucess2
# git
RUN echo "deb http://archive.debian.org/debian-backports squeeze-backports main" >> /etc/apt/sources.list
RUN apt-get update && echo success3
RUN apt-get install -y --force-yes -t squeeze-backports git && echo success4

# cleanup
RUN apt-get -y autoremove && echo success5
RUN apt-get -y clean && echo success6
RUN rm -rf /var/lib/apt/lists/*
