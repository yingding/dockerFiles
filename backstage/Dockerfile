###
#@Date Nov.30 2015
###
FROM ubuntu:14.04
MAINTAINER Yingding Wang "wang@pms.ifi.lmu.de"
# updating image repository references
RUN sudo apt-get update
# installing nodejs
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y nodejs
# installing node package manager
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y npm

# installing mongodb
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y mongodb

# installing add-apt-repository 
# Reference: http://askubuntu.com/questions/38021/how-to-add-a-ppa-on-a-server
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y software-properties-common
# installing Java8
RUN sudo add-apt-repository -y ppa:webupd8team/java
RUN sudo apt-get update
# enable silient install option 
# http://stackoverflow.com/questions/19275856/auto-yes-to-the-license-agreement-on-sudo-apt-get-y-install-oracle-java7-instal
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | sudo debconf-set-selections
RUN echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y oracle-java8-installer
# Set default
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y oracle-java8-set-default

