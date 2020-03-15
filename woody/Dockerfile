FROM debian/eol:woody

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y aptitude && aptitude install -y ssh tar gzip ca-certificates && echo success1
# git
RUN echo "deb http://archive.debian.org/debian-backports sarge-backports main" >> /etc/apt/sources.list
RUN apt-get update && echo success2
RUN apt-get install -y --force-yes -t sarge-backports git-core && echo success3

# cleanup
RUN apt-get -y clean && echo success4
