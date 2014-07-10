FROM centos:centos6
MAINTAINER ccg <ccgdevops@googlegroups.com>

RUN yum install -y http://yum.puppetlabs.com/puppetlabs-release-el-6.noarch.rpm
RUN yum --enablerepo=centosplus install -y puppet
RUN yum install -y mercurial git
RUN yum install -y http://mirror.aarnet.edu.au/pub/epel/6/i386/epel-release-6-8.noarch.rpm
RUN yum install -y http://dl.iuscommunity.org/pub/ius/stable/CentOS/6/x86_64/ius-release-1.0-11.ius.centos6.noarch.rpm
RUN yum install -y python27
RUN yum install -y ruby ruby-devel
RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN gem install librarian-puppet -v 1.0.4
