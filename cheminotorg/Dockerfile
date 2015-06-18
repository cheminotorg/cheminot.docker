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

# Prepare cheminotm

WORKDIR /app

RUN wget https://www.dropbox.com/s/fzy8ufv6bitxrlz/cheminotm-latest.zip?dl=1 -O cheminotm-latest.zip

RUN unzip cheminotm-latest.zip

# Prepare cheminotdb

RUN wget https://www.dropbox.com/s/wes1vv4cfqpyb2l/cheminotdb-latest.zip?dl=1 -O cheminotdb-latest.zip

RUN unzip cheminotdb-latest.zip

# Prepare cheminotorg

RUN wget https://www.dropbox.com/s/1ka5l21uwlw3lli/cheminotorg-latest.zip?dl=1 -O cheminotorg-latest.zip

RUN unzip cheminotorg-latest.zip

ADD run.sh /app/

RUN ldconfig /usr/local/lib

EXPOSE 9000

RUN sh /app/run.sh
