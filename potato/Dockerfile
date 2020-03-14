FROM lpenz/debian-potato-i386

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y git tar gzip && echo success1
RUN echo "deb http://archive.debian.org/debian woody main" >> /etc/apt/sources.list
RUN apt-get update && echo success2
RUN apt-get install -y ssh && echo success3
RUN apt-get install -y ca-certificates && echo success4

# cleanup
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list
RUN apt-get update && echo success5
