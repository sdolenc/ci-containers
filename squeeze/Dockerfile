FROM debian/eol:squeeze

# installs
RUN apt-get update && echo success1
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes ssh tar gzip ca-certificates && echo sucess2
# git
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN echo "deb http://archive.debian.org/debian wheezy main" > /etc/apt/sources.list
RUN apt-get update && echo success3
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes git && echo sucess4

# cleanup
RUN cp /etc/apt/sources.list.bak /etc/apt/sources.list
RUN apt-get update && echo success5
RUN apt-get -y autoremove && echo success6
RUN apt-get -y clean && echo success7
RUN rm -rf /var/lib/apt/lists/*
