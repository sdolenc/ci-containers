FROM debian/eol:etch

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN apt-get update && apt-get install -y aptitude && aptitude install -y ssh tar gzip ca-certificates && echo success1
# git
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN echo "deb http://archive.debian.org/debian lenny main" > /etc/apt/sources.list
RUN apt-get update && echo success2
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes git && echo sucess3

# cleanup
RUN cp /etc/apt/sources.list.bak /etc/apt/sources.list
RUN apt-get update && echo success4
RUN apt-get -y clean && echo success5
RUN rm -rf /var/lib/apt/lists/*
