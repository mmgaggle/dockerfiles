# debuilder
#
# VERSION               0.0.1

FROM      ubuntu
MAINTAINER Kyle Bader "kyle.bader@gmail.com"

# Setup base precise repos
#
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

# Install package building tools
#
RUN apt-get install -y devscripts ruby1.9.3 gem git vim less

RUN gem install fpm

