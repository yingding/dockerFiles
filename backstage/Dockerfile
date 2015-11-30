###
#@Date Nov.30 2015
###
FROM ubuntu:14.04
MAINTAINER Yingding Wang "wang@pms.ifi.lmu.de"
# updating image repository references
RUN sudo apt-get update
# installing nodejs
# run in non-interactive shell in docker
## http://askubuntu.com/questions/506158/unable-to-initialize-frontend-dialog-when-using-ssh
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y nodejs
# installing node package manager
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y npm

# installing mongodb
RUN sudo DEBIAN_FRONTEND=noninteractive apt-get install -y mongodb
# create the mongo db data directory
RUN mkdir -p /data/db
# EXPOSE port 27017 from the container to the host
EXPOSE 27017
# Set usr/bin/mongod as the dockerized entry-point application
# ENTRYPOINT ["/usr/bin/mongod"]

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


## Set dockerized entry-point
ENTRYPOINT ["/bin/bash"]
