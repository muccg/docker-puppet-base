# Use phusion/baseimage as base image. To make your builds reproducible, make
# sure you lock down to a specific version, not to `latest`!
# See https://github.com/phusion/baseimage-docker/blob/master/Changelog.md for
# a list of version numbers.
FROM phusion/baseimage:0.9.11
MAINTAINER ccg <ccgdevops@googlegroups.com>

# Set correct environment variables.
ENV HOME /root

# Regenerate SSH host keys. baseimage-docker does not contain any, so you
# have to do that yourself. You may also comment out this instruction; the
# init system will auto-generate one during boot.
RUN /etc/my_init.d/00_regen_ssh_host_keys.sh

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

# ...put your own build instructions here...
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get -y update -q
RUN apt-get install -y \
  build-essential \
  git \
  ruby ruby-dev

RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install puppet
RUN gem install librarian-puppet -v 1.0.4
RUN env --unset=DEBIAN_FRONTEND

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
