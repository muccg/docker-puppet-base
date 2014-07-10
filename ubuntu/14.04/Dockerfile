FROM ubuntu:14.04
MAINTAINER ccg <ccgdevops@googlegroups.com>

RUN apt-get -y update
RUN apt-get -y install python2.7
RUN apt-get -y install mercurial git
RUN apt-get -y install puppet
RUN apt-get -y install build-essential
RUN apt-get -y install ruby ruby-dev
RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install librarian-puppet -v 1.0.4
