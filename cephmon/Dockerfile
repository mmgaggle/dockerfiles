# cephmon
#
# VERSION               0.0.1

FROM      ubuntu
MAINTAINER Kyle Bader "kyle.bader@gmail.com"

# Setup base precise and Ceph repos
#
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN echo "deb http://gitbuilder.ceph.com/ceph-deb-precise-x86_64-basic/ref/bobtail precise main" > /etc/apt/sources.list.d/ceph.list
RUN apt-get update

# Install all the Ceph packages
#
RUN apt-get install -y librados2 librbd1 ceph-common ceph-common-dbg ceph ceph-dbg

# Ceph MON daemons listen on port 6789
#
EXPOSE 6789

# Start Ceph monitor
CMD /bin/ceph-mon -i $(hostname) --pid-file /var/run/ceph/mon.$(hostname).pid -c /etc/ceph/ceph.conf
