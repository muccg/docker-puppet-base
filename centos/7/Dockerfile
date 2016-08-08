FROM centos:centos7
MAINTAINER https://github.com/muccg

ENV PUPPET_VERSION 3.8.7
ENV LIBRARIAN_PUPPET_VERSION 2.2.3

RUN yum clean all && yum install -y \
  git \
  ruby \
  ruby-devel \
  rubygems \
  && yum clean all

RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install puppet -v ${PUPPET_VERSION}
RUN gem install librarian-puppet -v ${LIBRARIAN_PUPPET_VERSION}

ENTRYPOINT ["/bin/sh"]
