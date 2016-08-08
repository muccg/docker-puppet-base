FROM buildpack-deps:wily-curl
MAINTAINER https://github.com/muccg

ENV PUPPET_VERSION 3.8.7
ENV LIBRARIAN_PUPPET_VERSION 2.2.3

# install and use wget to fetch the package that does the puppetlabs repo setup
RUN apt-get update && apt-get install -qy --no-install-recommends \
   git \
   ruby \
   ruby-dev \
   rubygems \
   && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install puppet -v ${PUPPET_VERSION}
RUN gem install librarian-puppet -v ${LIBRARIAN_PUPPET_VERSION}

ENTRYPOINT ["/bin/sh"]
