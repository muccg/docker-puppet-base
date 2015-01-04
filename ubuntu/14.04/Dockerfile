FROM muccg/base:ubuntu14.04
MAINTAINER ccg <ccgdevops@googlegroups.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
  git \
  ruby \
  ruby-dev

RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install puppet
RUN gem install librarian-puppet -v 1.4.0

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
RUN env --unset=DEBIAN_FRONTEND
