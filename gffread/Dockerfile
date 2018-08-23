# Base image from Ubuntu #
FROM ubuntu:17.10

LABEL base.image="ubuntu:17.10"
LABEL software="gffread"
LABEL software.version="0.9.9"
LABEL maintainer="Mike Smith <msmith@bioneos.com>"

USER root

# Prep our container
RUN apt-get update && apt-get install curl -y

# Add gffread v 0.9.9, placed in /opt (using the static binary)
RUN mkdir /opt/gffread-0.9.9 && \
  curl -sL http://ccb.jhu.edu/software/stringtie/dl/gffread-0.9.9.Linux_x86_64.tar.gz | tar xz -C /opt/gffread-0.9.9 --strip-components=1

# Add our tool to the PATH
ENV PATH /opt/gffread-0.9.9/:$PATH

# Default command
CMD /bin/bash
