FROM debian/eol:lenny

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN apt-get update && apt-get install -y aptitude && aptitude install -y git ssh tar gzip ca-certificates && echo success1

# cleanup
RUN apt-get -y autoremove && echo success2
RUN apt-get -y clean && echo success3
