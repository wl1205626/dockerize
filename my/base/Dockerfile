#use centos7 as base os image
FROM wl:centos7

#author
MAINTAINER wanliang at 1803291739

# use aliyun yum repository
RUN curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
RUN yum clean all
RUN yum makecache

#install net-tools
RUN yum install -y net-tools

#install openssh-server
RUN yum install -y openssh-server

#start ssh service
##gen key
###gen redirect input file
RUN echo -e 'a\r\na' >ssh-ri
RUN ssh-keygen -t rsa  -f /etc/ssh/ssh_host_rsa_key <ssh-ri
RUN rm -rf ssh-ri
##start service
RUN /usr/sbin/sshd

CMD echo "Hello cmd!"
ENTRYPOINT echo "hello entry"
