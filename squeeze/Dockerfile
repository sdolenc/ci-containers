FROM lpenz/debian-squeeze-amd64

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN apt-get update && echo success1
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y aptitude && success2
RUN DEBIAN_FRONTEND=noninteractive aptitude install -y git ssh tar gzip ca-certificates && echo sucess3

# cleanup
RUN rm -rf /var/lib/apt/lists/*
