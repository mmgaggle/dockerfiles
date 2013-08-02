# thruk
#
# VERSION               0.0.1

FROM      ubuntu
MAINTAINER Kyle Bader "kyle.bader@gmail.com"

# Setup base precise repos
#
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

# Install apache and thruk
#
RUN apt-get install -y wget apache2 libcairo2 libcurl3 libgd2-xpm libmysqlclient18 libapache2-mod-fcgid cron logrotate xvfb
RUN wget http://www.thruk.org/files/pkg/v1.74-2/ubuntu12.04/amd64/thruk_1.74-2_ubuntu12.04_amd64.deb
RUN dpkg -i thruk_1.74-2_ubuntu12.04_amd64.deb

# Create apache user and directories
#
RUN mkdir -p /var/run/apache2 /var/apache2/lock

# Enable SSL
RUN a2ensite default-ssl
RUN a2enmod ssl

# Create self signed certificate
RUN apt-get install ssl-cert

# Only open port 443, we want SSL
EXPOSE 443

# Start up apache
CMD /usr/sbin/apache2 -k start
