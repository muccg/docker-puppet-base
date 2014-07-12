FROM centos:centos6
MAINTAINER ccg <ccgdevops@googlegroups.com>

RUN yum install -y http://yum.puppetlabs.com/puppetlabs-release-el-6.noarch.rpm
RUN yum --enablerepo=centosplus install -y puppet
RUN yum install -y \
  mercurial git \
  ruby ruby-devel \
  tar
RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install librarian-puppet -v 1.0.4

RUN yum clean all
