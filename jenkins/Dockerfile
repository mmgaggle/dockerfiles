# jenkins
#
# VERSION               0.0.1

FROM      ubuntu
MAINTAINER Kyle Bader "kyle.bader@gmail.com"

# Setup base precise repos
#
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y wget
RUN echo "deb http://pkg.jenkins-ci.org/debian binary/" > /etc/apt/sources.list.d/jenkins.list
RUN wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
RUN apt-get update

# Install Jenkins
#
RUN apt-get install -y jenkins

# Jenkins listens on 8080
#
EXPOSE 8080

CMD /usr/bin/java -jar /usr/share/jenkins/jenkins.war --webroot=/var/cache/jenkins/war --httpPort=8080 --ajp13Port=-1
