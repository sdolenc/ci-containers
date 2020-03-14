FROM debian/eol:potato

# remove security to help speed up apt-get (and reduce failures)
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list

# installs
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y git tar gzip && echo success1
# ssh
RUN echo "deb http://ftp.univ-nantes.fr/debian-non-US/ potato/non-US main" >> /etc/apt/sources.list
RUN apt-get update && echo success2
RUN apt-get install -y ssh || echo failed3
# ca-certificates
RUN echo "deb http://archive.debian.org/debian woody main" >> /etc/apt/sources.list
RUN apt-get update && echo success4
RUN apt-get install -y ca-certificates && echo success5

# cleanup
RUN grep -v "security" /etc/apt/sources.list.bak > /etc/apt/sources.list
RUN apt-get update && echo success6
