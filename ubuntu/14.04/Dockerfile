FROM muccg/base:ubuntu14.04
MAINTAINER ccg <ccgdevops@googlegroups.com>

ENV DEBIAN_FRONTEND noninteractive

# install and use wget to fetch the package that does the puppetlabs repo setup
RUN apt-get update && apt-get install -qy \
   wget \
   && wget --no-check-certificate https://apt.puppetlabs.com/puppetlabs-release-trusty.deb \
   && dpkg -i puppetlabs-release-trusty.deb \
   && rm puppetlabs-release-trusty.deb

# puppet labs repo should be configured at this layer
RUN apt-get update && apt-get install -qy \
  git \
  puppet \
  ruby \
  ruby-dev \
  && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN env --unset=DEBIAN_FRONTEND

# Install puppet librarian
# set version 1.4.0 if thats prefered
RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc && gem install librarian-puppet

