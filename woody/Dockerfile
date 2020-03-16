FROM debian/eol:woody

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y aptitude && aptitude install -y ssh tar gzip ca-certificates && echo success1
# git. this works, but circle can take care of this for us
# RUN aptitude install -y git-core && echo success2
