FROM debian/eol:potato

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN apt-get update && echo success0
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tar gzip && echo success1
# ca-certificates
RUN echo "deb http://archive.debian.org/debian woody main" >> /etc/apt/sources.list
RUN apt-get update && echo success2
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y ca-certificates && echo success3

# cleanup
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list
RUN apt-get update && echo success4
RUN apt-get -y clean && echo success5
