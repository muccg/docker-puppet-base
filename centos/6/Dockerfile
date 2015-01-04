FROM muccg/base:centos6
MAINTAINER ccg <ccgdevops@googlegroups.com>

RUN yum clean all && yum install -y \
  git \
  ruby \
  ruby-devel \
  rubygems

RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install puppet
RUN gem install librarian-puppet -v 1.4.0

RUN yum clean all
