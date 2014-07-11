FROM ubuntu:14.04
MAINTAINER ccg <ccgdevops@googlegroups.com>

ENV HOME /root
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LC_ALL en_US.UTF-8

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -y update -q
RUN apt-get install -y language-pack-en
RUN locale-gen en_US
RUN apt-get install -y \
  apt-transport-https ca-certificates \
  build-essential \
  git \
  ruby ruby-dev

RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install puppet
RUN gem install librarian-puppet -v 1.0.4

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN env --unset=DEBIAN_FRONTEND
