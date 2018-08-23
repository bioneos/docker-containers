# Base image from Ubuntu #
FROM ubuntu:17.10

LABEL base.image="ubuntu:17.10"
LABEL software="subread"
LABEL software.version="1.6.0"
LABEL maintainer="Mike Smith <msmith@bioneos.com>"

USER root

# Prep our container
RUN apt-get update && apt-get install curl -y

# Add subread v 1.6.0, placed in /opt (using the static binary)
RUN mkdir /opt/subread-1.6.0 && \
  curl -sL https://sourceforge.net/projects/subread/files/subread-1.6.0/subread-1.6.0-Linux-x86_64.tar.gz/download | tar xz -C /opt/subread-1.6.0 --strip-components=1

# Add our tool to the PATH
ENV PATH /opt/subread-1.6.0/bin:$PATH

# Default command
CMD /bin/bash
