FROM centos
MAINTAINER Kwok Yao Chim yaochim8@gmail.com
LABEL description="Baseline CentOS docker image"
LABEL version="1.0"
ENV container docker
RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;
VOLUME [ "/sys/fs/cgroup" ]
CMD ["/usr/sbin/init"]
RUN rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
RUN yum install -y nfs-utils autofs
RUN mkdir /var/www
RUN echo "/var/www /etc/auto.misc --timeout=50" >> /etc/auto.master
RUN echo "html -fstype=nfs4,minorversion=1,rw,nosuid,hard,tcp,timeo=60 us-west-2b.fs-32db239b.efs.us-west-2.amazonaws.com:/" >> /etc/auto.misc
RUN systemctl enable rpcbind
RUN systemctl enable autofs


