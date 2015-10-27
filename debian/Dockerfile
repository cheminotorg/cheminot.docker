FROM debian:latest

MAINTAINER Sebastien Renault <srenault.contact@gmail.com>

RUN apt-get -y update && apt-get -y upgrade

RUN apt-get -y install git

RUN apt-get -y install cmake

RUN apt-get -y install wget

RUN apt-get -y install curl

RUN apt-get -y install unzip

RUN apt-get -y install dh-autoreconf

RUN apt-get -y install libsqlite3-dev

RUN apt-get -y install openjdk-7-jdk

WORKDIR /app

# Build protobuf

RUN git clone https://github.com/google/protobuf.git

WORKDIR protobuf

RUN git checkout d4569d1f5ede96238dbb87b0ecc1fdcfbd399f62

RUN sh autogen.sh

RUN ./configure

RUN make && make install

# Build cheminot.c

WORKDIR /app

RUN git clone https://github.com/cheminotorg/m.cheminot.plugin.git

RUN git clone https://github.com/cheminotorg/cheminot.c.git

WORKDIR /app/cheminot.c/lib

RUN ln -s ../../protobuf/ protobuf

WORKDIR /app/cheminot.c/jni

RUN cmake .

RUN make

RUN ldconfig /usr/local/lib
