FROM lpenz/debian-squeeze-i386-minbase

# installs
RUN apt-get update && echo success1
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes git ssh tar gzip ca-certificates && echo sucess2

# cleanup
RUN rm -rf /var/lib/apt/lists/*
