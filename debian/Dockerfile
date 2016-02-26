FROM debian:8.3

MAINTAINER Sebastien Renault <srenault.contact@gmail.com>

RUN apt-get -y update && apt-get -y upgrade

RUN apt-get -y install wget

RUN apt-get -y install apt-transport-https ca-certificates

RUN apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D

RUN apt-get -y install openjdk-7-jdk

RUN wget -O - https://debian.neo4j.org/neotechnology.gpg.key | apt-key add -

RUN echo 'deb http://debian.neo4j.org/repo stable/' > /tmp/neo4j.list

RUN mv /tmp/neo4j.list /etc/apt/sources.list.d

RUN echo "deb https://apt.dockerproject.org/repo debian-jessie main" > /etc/apt/sources.list.d/docker.list

RUN apt-get -y update

RUN apt-cache policy docker-engine

RUN apt-get -y upgrade

RUN apt-get -y install docker-engine

RUN apt-get -y install neo4j=2.3.1
